
html_content = '''<!DOCTYPE html>
<html lang="it">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
<title>Cerchio di Luce</title>
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
  
  // Loop fluido: il colore scorre continuamente
  function getColors(t) {
    const shift = (t / DURATION) * 360;
    return [
      (0 + shift) % 360,
      (120 + shift) % 360,
      (240 + shift) % 360
    ];
  }
  
  function hsla(h, s, l, a) {
    return `hsla(${h}, ${s}%, ${l}%, ${a})`;
  }
  
  function draw() {
    const t = getTime();
    const w = canvas.width;
    const h = canvas.height;
    const cx = w / 2;
    const cy = h / 2;
    const baseRadius = Math.min(w, h) * 0.35;
    
    // PULSING DEL RAGGIO: ciclo che parte e finisce nello stesso punto
    const pulseCycles = 2;
    const pulsePhase = (t / DURATION) * pulseCycles * Math.PI * 2;
    const pulse = 1 + Math.sin(pulsePhase) * 0.05;
    const r = baseRadius * pulse;
    
    const hues = getColors(t);
    
    // Sfondo nero
    ctx.fillStyle = '#000';
    ctx.fillRect(0, 0, w, h);
    
    // --- TRE AREE con sfumatura radiale ---
    
    // Area 1: sinistra
    const g1 = ctx.createRadialGradient(cx - r * 0.25, cy - r * 0.1, 0, cx - r * 0.25, cy - r * 0.1, r * 0.9);
    g1.addColorStop(0, hsla(hues[0], 85, 65, 0.9));
    g1.addColorStop(0.5, hsla(hues[0], 85, 60, 0.7));
    g1.addColorStop(1, hsla(hues[0], 85, 55, 0));
    ctx.fillStyle = g1;
    ctx.beginPath();
    ctx.arc(cx - r * 0.25, cy - r * 0.1, r * 0.9, 0, Math.PI * 2);
    ctx.fill();
    
    // Area 2: destra
    const g2 = ctx.createRadialGradient(cx + r * 0.25, cy - r * 0.1, 0, cx + r * 0.25, cy - r * 0.1, r * 0.9);
    g2.addColorStop(0, hsla(hues[1], 85, 65, 0.9));
    g2.addColorStop(0.5, hsla(hues[1], 85, 60, 0.7));
    g2.addColorStop(1, hsla(hues[1], 85, 55, 0));
    ctx.fillStyle = g2;
    ctx.beginPath();
    ctx.arc(cx + r * 0.25, cy - r * 0.1, r * 0.9, 0, Math.PI * 2);
    ctx.fill();
    
    // Area 3: basso
    const g3 = ctx.createRadialGradient(cx, cy + r * 0.35, 0, cx, cy + r * 0.35, r * 0.9);
    g3.addColorStop(0, hsla(hues[2], 85, 65, 0.9));
    g3.addColorStop(0.5, hsla(hues[2], 85, 60, 0.7));
    g3.addColorStop(1, hsla(hues[2], 85, 55, 0));
    ctx.fillStyle = g3;
    ctx.beginPath();
    ctx.arc(cx, cy + r * 0.35, r * 0.9, 0, Math.PI * 2);
    ctx.fill();
    
    // --- ONDE fluide lungo il bordo con loop perfetto ---
    for (let i = 0; i < 4; i++) {
      const initialPhase = i * Math.PI / 2;
      // Cicli interi per entrambe le componenti
      const waveCycles = 2 + i;
      const alphaCycles = 2 + i;
      const alpha = 0.4 + Math.sin(initialPhase + (t / DURATION) * alphaCycles * Math.PI * 2) * 0.3;
      
      ctx.save();
      ctx.globalAlpha = alpha;
      ctx.lineWidth = 3;
      ctx.shadowBlur = 15;
      
      ctx.beginPath();
      for (let j = 0; j <= 200; j++) {
        const angle = (j / 200) * Math.PI * 2;
        // Entrambe le componenti sinusoidali con cicli interi
        const fastPhase = initialPhase + (t / DURATION) * waveCycles * Math.PI * 2;
        // slowCycles deve essere intero per avere loop perfetto
        const slowCycles = waveCycles; // stesso numero di cicli
        const slowPhase = initialPhase + (t / DURATION) * slowCycles * Math.PI * 2;
        const wave = Math.sin(angle * 6 + fastPhase) * (r * 0.08) * Math.sin(slowPhase);
        const rr = r + wave;
        const x = cx + Math.cos(angle) * rr;
        const y = cy + Math.sin(angle) * rr;
        if (j === 0) ctx.moveTo(x, y);
        else ctx.lineTo(x, y);
      }
      ctx.closePath();
      ctx.strokeStyle = hsla(hues[0], 80, 55, 1);
      ctx.shadowColor = ctx.strokeStyle;
      ctx.stroke();
      ctx.restore();
    }
    
    // --- PARTICELLE con loop perfetto e fase iniziale ---
    const particleCount = 20;
    for (let i = 0; i < particleCount; i++) {
      const initialPhase = (i / particleCount) * Math.PI * 2;
      const fullRotations = 1 + Math.floor(i / 3);
      const pAngle = initialPhase + (t / DURATION) * fullRotations * Math.PI * 2;
      
      const radialCycles = 1 + Math.floor(i / 4);
      const radialPhase = initialPhase * 0.7;
      const pRadius = r * (0.5 + Math.sin(radialPhase + (t / DURATION) * radialCycles * Math.PI * 2) * 0.3);
      
      const px = cx + Math.cos(pAngle) * pRadius;
      const py = cy + Math.sin(pAngle) * pRadius;
      
      const sizeCycles = 2 + Math.floor(i / 5);
      const sizePhase = initialPhase * 0.5;
      const size = 6 + Math.sin(sizePhase + (t / DURATION) * sizeCycles * Math.PI * 2) * 4;
      
      const alphaCycles = 1 + Math.floor(i / 3);
      const alphaPhase = initialPhase * 0.3;
      const alpha = 0.5 + Math.sin(alphaPhase + (t / DURATION) * alphaCycles * Math.PI * 2) * 0.3;
      
      const hue = hues[i % 3];
      
      ctx.save();
      ctx.globalAlpha = Math.max(0.1, Math.min(1, alpha));
      ctx.fillStyle = hsla(hue, 85, 60, 1);
      ctx.shadowColor = ctx.fillStyle;
      ctx.shadowBlur = 20;
      ctx.beginPath();
      ctx.arc(px, py, Math.max(1, size), 0, Math.PI * 2);
      ctx.fill();
      ctx.restore();
    }
    
    // --- BORDO cerchio con loop perfetto ---
    const glowCycles = 2;
    const glowPhase = (t / DURATION) * glowCycles * Math.PI * 2;
    const borderGlow = 25 + Math.sin(glowPhase) * 10;
    
    ctx.save();
    ctx.lineWidth = 4;
    ctx.shadowBlur = borderGlow;
    ctx.strokeStyle = hsla(hues[0], 80, 55, 1);
    ctx.shadowColor = ctx.strokeStyle;
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

with open('/mnt/agents/output/cerchio_luce_v23.html', 'w', encoding='utf-8') as f:
    f.write(html_content)


