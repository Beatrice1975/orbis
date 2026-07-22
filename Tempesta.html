
html_content = '''<!DOCTYPE html>
<html lang="it">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
<title>Temporale dal Basso</title>
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }
  body {
    background: #000;
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    width: 100vw;
  }
  canvas { display: block; }
</style>
</head>
<body>
<canvas id="c"></canvas>
<script>
  const canvas = document.getElementById('c');
  const ctx = canvas.getContext('2d');
  
  function resize() {
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
  }
  resize();
  window.addEventListener('resize', resize);
  
  const DURATION = 30;
  
  function getTime() {
    return (performance.now() / 1000) % DURATION;
  }
  
  function seededRandom(seed) {
    const x = Math.sin(seed * 127.1 + 311.7) * 43758.5453;
    return x - Math.floor(x);
  }
  
  const RAINDROPS = 50;
  
  function getRaindrop(t, i) {
    const angleSeed = i * 7.3 + 1.1;
    const angle = seededRandom(angleSeed) * Math.PI * 2;
    const speedSeed = i * 3.7 + 2.9;
    const speed = 0.4 + seededRandom(speedSeed) * 0.6;
    
    const dropsPerDuration = 5 + Math.floor(i / 3);
    const dropPhase = (t / DURATION) * dropsPerDuration;
    const progress = dropPhase % 1;
    
    const dist = 0.05 + progress * 0.95;
    const sizeBase = 1.5 + progress * 4.0;
    const lengthBase = 0.01 + progress * 0.06;
    const alpha = 0.6 + Math.sin(progress * Math.PI) * 0.35;
    
    // Fase di impatto: piu' lunga per vedere meglio
    const impactProgress = Math.max(0, (progress - 0.88) / 0.12);
    
    return { angle, dist, progress, sizeBase, lengthBase, alpha, speed, impactProgress };
  }
  
  const LIGHTNING_DATA = [
    { time: 4.2, duration: 0.22 },
    { time: 12.7, duration: 0.35 },
    { time: 23.1, duration: 0.18 }
  ];
  
  function getLightning(t) {
    for (let i = 0; i < LIGHTNING_DATA.length; i++) {
      const lt = LIGHTNING_DATA[i].time;
      const ld = LIGHTNING_DATA[i].duration;
      if (t >= lt && t < lt + ld) {
        const progress = (t - lt) / ld;
        return Math.sin(progress * Math.PI);
      }
    }
    return 0;
  }
  
  function getSkyGlow(t) {
    const glows = [
      { start: 6, end: 11 },
      { start: 17, end: 23 }
    ];
    for (let i = 0; i < glows.length; i++) {
      const g = glows[i];
      if (t >= g.start && t < g.end) {
        const progress = (t - g.start) / (g.end - g.start);
        return Math.sin(progress * Math.PI) * 0.5;
      }
    }
    return 0;
  }
  
  function draw() {
    const t = getTime();
    const w = canvas.width;
    const h = canvas.height;
    const cx = w / 2;
    const cy = h / 2;
    const baseRadius = Math.min(w, h) * 0.35;
    const r = baseRadius;
    
    const lightning = getLightning(t);
    const skyGlow = getSkyGlow(t);
    
    ctx.fillStyle = '#000';
    ctx.fillRect(0, 0, w, h);
    
    ctx.save();
    ctx.beginPath();
    ctx.arc(cx, cy, r, 0, Math.PI * 2);
    ctx.clip();
    
    if (skyGlow > 0) {
      const glowGrad = ctx.createRadialGradient(cx, cy, 0, cx, cy, r);
      glowGrad.addColorStop(0, `rgba(220, 225, 235, ${skyGlow * 0.9})`);
      glowGrad.addColorStop(0.5, `rgba(190, 195, 205, ${skyGlow * 0.5})`);
      glowGrad.addColorStop(1, `rgba(160, 165, 175, ${skyGlow * 0.2})`);
      ctx.fillStyle = glowGrad;
      ctx.fillRect(cx - r, cy - r, r * 2, r * 2);
    }
    
    const stormGrad = ctx.createRadialGradient(cx, cy, 0, cx, cy, r);
    const stormLightness = 3 + lightning * 40 + skyGlow * 35;
    stormGrad.addColorStop(0, `hsla(220, 50%, ${stormLightness}%, 0.25)`);
    stormGrad.addColorStop(0.5, `hsla(230, 60%, ${stormLightness * 0.7}%, 0.15)`);
    stormGrad.addColorStop(1, 'hsla(240, 80%, 2%, 0)');
    
    ctx.fillStyle = stormGrad;
    ctx.beginPath();
    ctx.arc(cx, cy, r, 0, Math.PI * 2);
    ctx.fill();
    
    if (lightning > 0) {
      ctx.save();
      ctx.globalAlpha = lightning * 0.95;
      const lightningSeed = Math.floor(t);
      for (let b = 0; b < 4; b++) {
        ctx.beginPath();
        let lx = cx + (seededRandom(lightningSeed + b * 13) - 0.5) * r * 0.8;
        let ly = cy + (seededRandom(lightningSeed + b * 13 + 1) - 0.5) * r * 0.8;
        ctx.moveTo(lx, ly);
        for (let s = 0; s < 6; s++) {
          lx += (seededRandom(lightningSeed + b * 13 + s * 7) - 0.5) * r * 0.3;
          ly += (seededRandom(lightningSeed + b * 13 + s * 7 + 3) - 0.5) * r * 0.3;
          ctx.lineTo(lx, ly);
        }
        ctx.strokeStyle = `hsla(195, 100%, ${90 + lightning * 10}%, ${lightning})`;
        ctx.lineWidth = 1 + lightning * 5;
        ctx.shadowColor = '#fff';
        ctx.shadowBlur = 30 * lightning;
        ctx.stroke();
      }
      ctx.restore();
    }
    
    for (let i = 0; i < RAINDROPS; i++) {
      const drop = getRaindrop(t, i);
      const dist = drop.dist * r;
      const px = cx + Math.cos(drop.angle) * dist;
      const py = cy + Math.sin(drop.angle) * dist;
      const dropLen = drop.lengthBase * r;
      const dx = -Math.cos(drop.angle) * dropLen;
      const dy = -Math.sin(drop.angle) * dropLen;
      const size = drop.sizeBase;
      
      // --- GOCCIA CHE CADE ---
      if (drop.progress < 0.95) {
        ctx.save();
        ctx.globalAlpha = drop.alpha;
        const dropLightness = 92 + lightning * 8 + skyGlow * 8;
        const dropSat = 20 + lightning * 15;
        ctx.strokeStyle = `hsla(205, ${dropSat}%, ${dropLightness}%, ${drop.alpha})`;
        ctx.lineWidth = size;
        ctx.lineCap = 'round';
        ctx.shadowColor = `hsla(200, 100%, 98%, ${0.6 + lightning * 0.4})`;
        ctx.shadowBlur = size * 4;
        ctx.beginPath();
        ctx.moveTo(px, py);
        ctx.lineTo(px + dx, py + dy);
        ctx.stroke();
        ctx.restore();
      }
      
      // --- IMPATTO goccia ---
      if (drop.impactProgress > 0) {
        const impactAlpha = (1 - drop.impactProgress) * drop.alpha;
        
        // Cerchio di impatto che si espande MOLTO di piu'
        const impactSize = size * (1 + drop.impactProgress * 5);
        
        ctx.save();
        ctx.globalAlpha = impactAlpha * 0.9;
        ctx.strokeStyle = `hsla(205, 40%, 90%, ${impactAlpha})`;
        ctx.lineWidth = 2;
        ctx.shadowColor = `hsla(200, 100%, 95%, 0.8)`;
        ctx.shadowBlur = impactSize * 3;
        ctx.beginPath();
        ctx.arc(px, py, impactSize, 0, Math.PI * 2);
        ctx.stroke();
        ctx.restore();
        
        // Cerchio interno
        ctx.save();
        ctx.globalAlpha = impactAlpha * 0.4;
        ctx.fillStyle = `hsla(205, 30%, 95%, ${impactAlpha * 0.5})`;
        ctx.beginPath();
        ctx.arc(px, py, impactSize * 0.5, 0, Math.PI * 2);
        ctx.fill();
        ctx.restore();
        
        // Schizzi pioggia
        const splashCount = 6;
        for (let s = 0; s < splashCount; s++) {
          const splashAngle = drop.angle + (seededRandom(i * 13 + s * 7) - 0.5) * Math.PI * 1.2;
          const splashDist = drop.impactProgress * size * 4;
          const sx = px + Math.cos(splashAngle) * splashDist;
          const sy = py + Math.sin(splashAngle) * splashDist;
          const splashSize = size * 0.6 * (1 - drop.impactProgress);
          
          ctx.save();
          ctx.globalAlpha = impactAlpha * 0.9;
          ctx.fillStyle = `hsla(205, 25%, 92%, ${impactAlpha})`;
          ctx.shadowColor = `hsla(200, 100%, 95%, 0.7)`;
          ctx.shadowBlur = splashSize * 3;
          ctx.beginPath();
          ctx.arc(sx, sy, splashSize, 0, Math.PI * 2);
          ctx.fill();
          ctx.restore();
        }
      }
    }
    
    const cloudGrad = ctx.createRadialGradient(cx, cy, 0, cx, cy, r * 0.5);
    const cloudLightness = 5 + lightning * 30 + skyGlow * 25;
    cloudGrad.addColorStop(0, `hsla(230, 30%, ${cloudLightness}%, 0.35)`);
    cloudGrad.addColorStop(1, 'transparent');
    ctx.fillStyle = cloudGrad;
    ctx.beginPath();
    ctx.arc(cx, cy, r * 0.5, 0, Math.PI * 2);
    ctx.fill();
    
    ctx.restore();
    
    const borderLightness = 8 + lightning * 50 + skyGlow * 25;
    ctx.save();
    ctx.lineWidth = 3;
    ctx.shadowBlur = 10 + lightning * 30;
    ctx.strokeStyle = `hsla(220, 50%, ${borderLightness}%, 0.8)`;
    ctx.shadowColor = `hsla(200, 100%, ${borderLightness}%, ${0.3 + lightning * 0.7})`;
    ctx.beginPath();
    ctx.arc(cx, cy, r, 0, Math.PI * 2);
    ctx.stroke();
    ctx.restore();
    
    requestAnimationFrame(draw);
  }
  
  draw();
</script>
</body>
</html>'''

with open('/mnt/agents/output/temporale_dal_basso.html', 'w', encoding='utf-8') as f:
    f.write(html_content)


