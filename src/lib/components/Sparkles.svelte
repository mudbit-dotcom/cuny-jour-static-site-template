<script>
  import { onMount } from 'svelte';

  let canvas;
  let ctx;
  let particles = [];

  function createParticle(x, y) {
    particles.push({
      x, y,
      size: Math.random() * 8 + 4,
      speedX: (Math.random() - 0.5) * 4,
      speedY: (Math.random() - 0.5) * 4 - 2,
      opacity: 1,
      color: ['#ff69b4', '#bf94e4', '#fffacd', '#ffffff'][Math.floor(Math.random() * 4)]
    });
  }

  function animate() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    particles = particles.filter(p => p.opacity > 0);
    for (let p of particles) {
      ctx.save();
      ctx.globalAlpha = p.opacity;
      ctx.fillStyle = p.color;
      ctx.font = `${p.size * 2}px serif`;
      ctx.fillText('✦', p.x, p.y);
      ctx.restore();
      p.x += p.speedX;
      p.y += p.speedY;
      p.opacity -= 0.03;
    }
    requestAnimationFrame(animate);
  }

  onMount(() => {
    ctx = canvas.getContext('2d');
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
    window.addEventListener('resize', () => {
      canvas.width = window.innerWidth;
      canvas.height = window.innerHeight;
    });
    animate();
  });

  function handleMouse(e) {
    for (let i = 0; i < 3; i++) createParticle(e.clientX, e.clientY);
  }
</script>

<svelte:window onmousemove={handleMouse} />

<canvas bind:this={canvas}></canvas>

<style>
  canvas {
    position: fixed;
    top: 0;
    left: 0;
    pointer-events: none;
    z-index: 9999;
  }
</style>