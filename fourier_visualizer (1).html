<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Визуализатор Фурье — Звуковые колебания</title>
<style>
*{box-sizing:border-box;margin:0;padding:0}
body{font-family:'Segoe UI',system-ui,sans-serif;background:#0d1117;color:#e0e8f0;min-height:100vh;padding:20px}
h1{font-size:17px;font-weight:500;text-align:center;color:#7fb3e8;margin-bottom:4px;letter-spacing:0.5px}
.subtitle{font-size:11px;text-align:center;color:#3d5070;margin-bottom:16px}
.wrap{max-width:920px;margin:0 auto}
.metrics{display:grid;grid-template-columns:repeat(4,1fr);gap:10px;margin-bottom:14px}
.met{background:#161c27;border:0.5px solid #2a3448;border-radius:10px;padding:10px 14px}
.met-label{font-size:11px;color:#5a7090;margin-bottom:4px}
.met-val{font-size:20px;font-weight:500;color:#e0e8f0}
.met-val.ok{color:#3ecf8e}
.met-val.warn{color:#f0a830}
.met-val.bad{color:#e05a5a}
.panels{display:grid;grid-template-columns:1fr 1fr;gap:12px;margin-bottom:12px}
.card{background:#161c27;border:0.5px solid #2a3448;border-radius:12px;padding:14px 16px}
.card-title{font-size:12px;color:#5a7090;margin-bottom:10px}
.ctrl-row{display:flex;align-items:center;gap:10px;margin-bottom:12px}
.ctrl-row:last-child{margin-bottom:0}
.ctrl-label{font-size:12px;color:#8aa0bc;min-width:130px}
.ctrl-val{font-size:12px;font-weight:500;color:#7fb3e8;min-width:36px;text-align:right}
input[type=range]{flex:1;-webkit-appearance:none;height:4px;border-radius:2px;background:#2a3448;outline:none;cursor:pointer}
input[type=range]::-webkit-slider-thumb{-webkit-appearance:none;width:14px;height:14px;border-radius:50%;background:#378ADD;cursor:pointer;border:2px solid #0d1117}
input[type=range]::-webkit-slider-thumb:hover{background:#5DCAA5}
.tbtn-group{display:flex;gap:6px;margin-bottom:12px}
.tbtn{padding:5px 12px;font-size:11px;font-weight:500;border:0.5px solid #2a3448;border-radius:8px;background:transparent;color:#5a7090;cursor:pointer;transition:all .15s}
.tbtn.active{background:#185FA5;border-color:#378ADD;color:#B5D4F4}
.tbtn:hover:not(.active){background:#1e2840;color:#8aa0bc}
.action-btns{display:flex;gap:8px;margin-bottom:12px;flex-wrap:wrap}
.abtn{padding:6px 14px;font-size:12px;font-weight:500;border:0.5px solid #2a3448;border-radius:8px;background:transparent;color:#8aa0bc;cursor:pointer;transition:all .15s}
.abtn:hover{background:#1e2840;color:#e0e8f0}
.abtn.active-clip{background:#7B2B1D;border-color:#D85A30;color:#F5C4B3}
.abtn.play-active{background:#0F3D2A;border-color:#3ecf8e;color:#3ecf8e}
.canvas-card{background:#161c27;border:0.5px solid #2a3448;border-radius:12px;padding:14px 16px;margin-bottom:12px}
.canvas-label{font-size:11px;color:#5a7090;margin-bottom:8px;display:flex;align-items:center;gap:8px}
.badge{font-size:10px;padding:2px 8px;border-radius:6px;font-weight:500}
.badge-blue{background:#0C447C;color:#B5D4F4}
.badge-red{background:#791F1F;color:#F7C1C1}
.badge-amber{background:#633806;color:#FAC775}
canvas{display:block;width:100%;border-radius:8px;background:#080c14}
.harm-mini{display:flex;gap:2px;align-items:flex-end;height:28px;margin-top:8px}
.hb{border-radius:2px 2px 0 0;min-height:2px;transition:height .18s,background .18s}

/* Tables */
.data-section{background:#161c27;border:0.5px solid #2a3448;border-radius:12px;padding:16px;margin-bottom:12px}
.data-section h3{font-size:12px;color:#5a7090;margin-bottom:12px;font-weight:500}
.tables-grid{display:grid;grid-template-columns:1fr 1fr;gap:12px}
table{width:100%;border-collapse:collapse;font-size:11px}
thead tr{background:#0d1117}
th{padding:7px 8px;text-align:center;color:#5a7090;font-weight:500;border-bottom:0.5px solid #2a3448}
td{padding:6px 8px;text-align:center;border-bottom:0.5px solid #1a2438;color:#c0d0e0}
.t-odd{color:#EF9F27;font-weight:600}
.t-base{color:#378ADD;font-weight:600}
.t-change-up{color:#e05a5a}
.kni-row{display:flex;gap:12px;margin-top:14px}
.kni-box{flex:1;background:#0d1117;border:0.5px solid #2a3448;border-radius:8px;padding:10px 14px;text-align:center}
.kni-label{font-size:10px;color:#5a7090;margin-bottom:4px}
.kni-val{font-size:22px;font-weight:600}
.kni-clean{color:#3ecf8e}
.kni-dist{color:#e05a5a}
.info-note{font-size:10px;color:#3d5070;margin-top:8px;line-height:1.5}

@media(max-width:600px){.panels{grid-template-columns:1fr}.metrics{grid-template-columns:1fr 1fr}.tables-grid{grid-template-columns:1fr}}
</style>
</head>
<body>
<div class="wrap">
  <h1>Визуализатор физики звука — синтез Фурье и дисторшн</h1>
  <div class="subtitle">Индивидуальный проект · Кучеренко М.Е. · «Звуковые колебания. Физический смысл и музыкальное искусство»</div>

  <div class="metrics">
    <div class="met"><div class="met-label">Гармоник</div><div class="met-val" id="mH">1</div></div>
    <div class="met"><div class="met-label">Амплитуда</div><div class="met-val" id="mA">80%</div></div>
    <div class="met"><div class="met-label">КНИ (THD)</div><div class="met-val ok" id="mT">0.00%</div></div>
    <div class="met"><div class="met-label">Форма волны</div><div class="met-val" id="mW" style="font-size:13px;line-height:1.5">Чистый синус</div></div>
  </div>

  <div class="action-btns">
    <button class="abtn play-active" id="playBtn">⏸ Пауза</button>
    <button class="abtn" id="clipBtn">Клиппинг выкл.</button>
  </div>

  <div class="panels">
    <div class="card">
      <div class="card-title">Синтез Фурье</div>
      <div class="ctrl-row">
        <span class="ctrl-label">Гармоник</span>
        <input type="range" id="harmonics" min="1" max="30" value="1" step="1">
        <span class="ctrl-val" id="hv">1</span>
      </div>
      <div class="ctrl-row">
        <span class="ctrl-label">Амплитуда</span>
        <input type="range" id="amplitude" min="0" max="100" value="80" step="1">
        <span class="ctrl-val" id="av">80</span>
      </div>
      <div class="ctrl-row">
        <span class="ctrl-label">Скорость анимации</span>
        <input type="range" id="speed" min="1" max="10" value="4" step="1">
        <span class="ctrl-val" id="sv">4</span>
      </div>
      <div class="harm-mini" id="harmBars"></div>
    </div>
    <div class="card">
      <div class="card-title">Тип сигнала и клиппинг</div>
      <div class="tbtn-group">
        <button class="tbtn active" data-type="all">Все гармоники (пила)</button>
        <button class="tbtn" data-type="odd">Нечётные (меандр)</button>
      </div>
      <div class="ctrl-row">
        <span class="ctrl-label">Порог клиппинга</span>
        <input type="range" id="clipLevel" min="10" max="100" value="60" step="1">
        <span class="ctrl-val" id="cv">60</span>
      </div>
      <p style="font-size:10px;color:#3d5070;line-height:1.5;margin-top:8px">
        При клиппинге амплитуда волны «срезается», форма приближается к меандру — происходит лавинообразный синтез нечётных гармоник (дисторшн).
      </p>
    </div>
  </div>

  <div class="canvas-card">
    <div class="canvas-label">
      Осциллограмма
      <span class="badge badge-amber" id="bdWave">Чистый синус</span>
      <span class="badge badge-red" id="bdClip" style="display:none">Клиппинг активен</span>
    </div>
    <canvas id="waveCanvas" height="160"></canvas>
  </div>

  <div class="canvas-card">
    <div class="canvas-label">
      Частотный спектр (БПФ)
      <span class="badge badge-blue" id="bdHarm">1 гармоника</span>
    </div>
    <canvas id="specCanvas" height="170"></canvas>
  </div>

  <div class="canvas-card">
    <div class="canvas-label">Круговые фазоры (вращение гармоник)</div>
    <canvas id="phasorCanvas" height="220"></canvas>
  </div>

  <!-- Экспериментальные данные из проекта -->
  <div class="data-section">
    <h3>Результаты эксперимента — нота A₂ (110 Гц), сравнительный анализ спектра</h3>
    <div class="tables-grid">
      <div>
        <table>
          <caption style="font-size:10px;color:#3ecf8e;text-align:left;padding-bottom:6px">Таблица 1. Clean — чистый сигнал</caption>
          <thead><tr><th>n</th><th>Частота, Гц</th><th>Тип</th><th>Амплитуда (отн.)</th></tr></thead>
          <tbody>
            <tr><td class="t-base">1</td><td>110</td><td>Осн. тон</td><td class="t-base">1,00</td></tr>
            <tr><td>2</td><td>220</td><td>Чётная</td><td>0,55</td></tr>
            <tr><td class="t-odd">3</td><td>330</td><td>Нечётная</td><td class="t-odd">0,12</td></tr>
            <tr><td>4</td><td>440</td><td>Чётная</td><td>0,15</td></tr>
            <tr><td class="t-odd">5</td><td>550</td><td>Нечётная</td><td class="t-odd">0,05</td></tr>
          </tbody>
        </table>
      </div>
      <div>
        <table>
          <caption style="font-size:10px;color:#e05a5a;text-align:left;padding-bottom:6px">Таблица 2. Distortion — сигнал с клиппингом</caption>
          <thead><tr><th>n</th><th>Частота, Гц</th><th>Тип</th><th>Амплитуда</th><th>Изменение</th></tr></thead>
          <tbody>
            <tr><td class="t-base">1</td><td>110</td><td>Осн. тон</td><td class="t-base">1,00</td><td style="color:#5a7090">—</td></tr>
            <tr><td>2</td><td>220</td><td>Чётная</td><td>0,60</td><td style="color:#8aa0bc">↑ незначит.</td></tr>
            <tr><td class="t-odd">3</td><td>330</td><td>Нечётная</td><td class="t-odd">0,85</td><td class="t-change-up">+608%</td></tr>
            <tr><td>4</td><td>440</td><td>Чётная</td><td>0,25</td><td style="color:#8aa0bc">↑ умерен.</td></tr>
            <tr><td class="t-odd">5</td><td>550</td><td>Нечётная</td><td class="t-odd">0,58</td><td class="t-change-up">+1060%</td></tr>
            <tr><td class="t-odd">7</td><td>770</td><td>Нечётная</td><td class="t-odd">0,45</td><td class="t-change-up">синтез. заново</td></tr>
          </tbody>
        </table>
      </div>
    </div>

    <div class="kni-row">
      <div class="kni-box">
        <div class="kni-label">КНИ — Clean</div>
        <div class="kni-val kni-clean">≈ 58%</div>
        <div class="info-note">Естественные обертоны колеблющейся струны. Чётные гармоники преобладают — консонансное, «округлое» звучание.</div>
      </div>
      <div class="kni-box">
        <div class="kni-label">КНИ — Distortion</div>
        <div class="kni-val kni-dist">≈ 121,7%</div>
        <div class="info-note">Рост &gt;2× по сравнению с Clean. Лавинообразный синтез нечётных гармоник при клиппинге — «агрессивный» тембр дисторшна.</div>
      </div>
    </div>

    <p class="info-note" style="margin-top:12px">
      <strong style="color:#5a7090">Формула КНИ:</strong>&nbsp;
      K<sub>h</sub> = √(A₂² + A₃² + ... + Aₙ²) / A₁ × 100%&nbsp;&nbsp;|&nbsp;&nbsp;
      <strong style="color:#5a7090">Ряд Фурье:</strong>&nbsp;
      f(t) = a₀/2 + Σ[aₙcos(nωt) + bₙsin(nωt)]
    </p>
  </div>

</div>

<script>
const wC=document.getElementById('waveCanvas'),sC=document.getElementById('specCanvas'),pC=document.getElementById('phasorCanvas');
const wX=wC.getContext('2d'),sX=sC.getContext('2d'),pX=pC.getContext('2d');
const harmInput=document.getElementById('harmonics'),ampInput=document.getElementById('amplitude');
const clipLvl=document.getElementById('clipLevel'),speedInput=document.getElementById('speed');
const clipBtn=document.getElementById('clipBtn'),playBtn=document.getElementById('playBtn');

let isClipping=false,isPlaying=true,harmType='all',phase=0,raf=null;

function resize(){
  [wC,sC,pC].forEach(c=>{c.width=c.offsetWidth;c.height=c.offsetHeight||160});
}
window.addEventListener('resize',()=>{resize();});
resize();

document.querySelectorAll('.tbtn').forEach(b=>{
  b.onclick=()=>{
    document.querySelectorAll('.tbtn').forEach(x=>x.classList.remove('active'));
    b.classList.add('active');harmType=b.dataset.type;
  };
});

clipBtn.onclick=()=>{
  isClipping=!isClipping;
  clipBtn.textContent=isClipping?'Клиппинг вкл.':'Клиппинг выкл.';
  clipBtn.className=isClipping?'abtn active-clip':'abtn';
  document.getElementById('bdClip').style.display=isClipping?'':'none';
};

playBtn.onclick=()=>{
  isPlaying=!isPlaying;
  playBtn.textContent=isPlaying?'⏸ Пауза':'▶ Играть';
  playBtn.className=isPlaying?'abtn play-active':'abtn';
  if(isPlaying)loop();
};

[harmInput,ampInput,clipLvl,speedInput].forEach(el=>el.oninput=updateLabels);

function updateLabels(){
  document.getElementById('hv').textContent=harmInput.value;
  document.getElementById('av').textContent=ampInput.value;
  document.getElementById('cv').textContent=clipLvl.value;
  document.getElementById('sv').textContent=speedInput.value;
  document.getElementById('mH').textContent=harmInput.value;
  document.getElementById('mA').textContent=ampInput.value+'%';
  const n=parseInt(harmInput.value);
  document.getElementById('bdHarm').textContent=n+(n===1?' гармоника':n<5?' гармоники':' гармоник');
}

function drawGrid(ctx,w,h,rows=6,cols=8){
  ctx.strokeStyle='rgba(255,255,255,0.04)';ctx.lineWidth=0.5;
  for(let i=1;i<rows;i++){const y=h/rows*i;ctx.beginPath();ctx.moveTo(0,y);ctx.lineTo(w,y);ctx.stroke();}
  for(let i=1;i<cols;i++){const x=w/cols*i;ctx.beginPath();ctx.moveTo(x,0);ctx.lineTo(x,h);ctx.stroke();}
  ctx.strokeStyle='rgba(255,255,255,0.12)';ctx.lineWidth=1;
  ctx.beginPath();ctx.moveTo(0,h/2);ctx.lineTo(w,h/2);ctx.stroke();
}

function getAmps(nH,type,ampPx){
  const amps=[];
  for(let i=1;i<=nH;i++){
    const n=type==='odd'?(2*i-1):i;
    amps.push({n,a:ampPx/n});
  }
  return amps;
}

function drawWave(t){
  const W=wC.width,H=wC.height;
  const nH=parseInt(harmInput.value);
  const ampPx=(parseInt(ampInput.value)/100)*(H/3);
  const threshold=(parseInt(clipLvl.value)/100)*(H/3);
  const spd=parseInt(speedInput.value)*0.004;

  wX.clearRect(0,0,W,H);
  wX.fillStyle='#080c14';wX.fillRect(0,0,W,H);
  drawGrid(wX,W,H);

  if(isClipping){
    wX.setLineDash([4,4]);
    wX.strokeStyle='rgba(208,90,48,0.5)';wX.lineWidth=1;
    wX.beginPath();wX.moveTo(0,H/2-threshold);wX.lineTo(W,H/2-threshold);wX.stroke();
    wX.beginPath();wX.moveTo(0,H/2+threshold);wX.lineTo(W,H/2+threshold);wX.stroke();
    wX.setLineDash([]);
  }

  const amps=getAmps(nH,harmType,ampPx);

  if(isClipping&&ampPx>threshold){
    wX.beginPath();wX.strokeStyle='rgba(216,90,48,0.2)';wX.lineWidth=1.5;
    for(let x=0;x<W;x++){
      let y=0;
      for(const {n,a} of amps) y+=a*Math.sin(2*Math.PI*n*(x/W)*2+t*n);
      x===0?wX.moveTo(x,H/2-y):wX.lineTo(x,H/2-y);
    }
    wX.stroke();
  }

  const grd=wX.createLinearGradient(0,0,W,0);
  if(isClipping){grd.addColorStop(0,'#EF9F27');grd.addColorStop(0.5,'#e05a5a');grd.addColorStop(1,'#EF9F27');}
  else{grd.addColorStop(0,'#378ADD');grd.addColorStop(0.5,'#5DCAA5');grd.addColorStop(1,'#378ADD');}

  wX.beginPath();wX.strokeStyle=grd;wX.lineWidth=2;
  for(let x=0;x<W;x++){
    let y=0;
    for(const {n,a} of amps) y+=a*Math.sin(2*Math.PI*n*(x/W)*2+t*n);
    if(isClipping) y=Math.max(-threshold,Math.min(threshold,y));
    x===0?wX.moveTo(x,H/2-y):wX.lineTo(x,H/2-y);
  }
  wX.stroke();

  wX.fillStyle='rgba(120,160,200,0.5)';wX.font='10px sans-serif';
  wX.fillText('+',6,14);wX.fillText('0',6,H/2+4);wX.fillText('−',6,H-8);
}

function drawSpec(t){
  const W=sC.width,H=sC.height;
  const nH=parseInt(harmInput.value);
  const ampPx=(parseInt(ampInput.value)/100)*(H/2.5);
  const amps=getAmps(nH,harmType,ampPx);

  sX.clearRect(0,0,W,H);
  sX.fillStyle='#080c14';sX.fillRect(0,0,W,H);
  drawGrid(sX,W,H,5,10);

  const maxN=harmType==='odd'?(2*nH-1):nH;
  const displayMax=Math.max(maxN+2,10);
  const barW=W/(displayMax+1);

  for(const {n,a} of amps){
    const pct=a/amps[0].a;
    const pulse=1+0.06*Math.sin(t*n*2);
    const h=pct*pulse*(H-45);
    const x=n*barW+barW*0.1;
    const bw=barW*0.8;
    const color=n===1?'#378ADD':(n%2===0?'#5DCAA5':'#EF9F27');
    sX.fillStyle=color+'bb';
    sX.fillRect(x,H-30-h,bw,h);
    sX.fillStyle=color;
    sX.fillRect(x,H-30-h,bw,3);
    sX.fillStyle='rgba(180,210,240,0.55)';sX.font='9px sans-serif';sX.textAlign='center';
    sX.fillText(n,x+bw/2,H-14);
    if(pct>0.07){sX.fillStyle=color;sX.fillText((pct*100).toFixed(0)+'%',x+bw/2,H-32-h);}
  }
  sX.textAlign='left';

  const leg=[{c:'#378ADD',l:'Основная'},{c:'#EF9F27',l:'Нечётные'},{c:'#5DCAA5',l:'Чётные'}];
  leg.forEach((l,i)=>{
    sX.fillStyle=l.c;sX.fillRect(8+i*90,8,8,8);
    sX.fillStyle='rgba(140,170,200,0.7)';sX.font='9px sans-serif';
    sX.fillText(l.l,20+i*90,16);
  });
}

function drawPhasor(t){
  const W=pC.width,H=pC.height;
  const nH=Math.min(parseInt(harmInput.value),8);
  const ampPx=Math.min(H,W)*0.28;
  const ampScale=(parseInt(ampInput.value)/100);

  pX.clearRect(0,0,W,H);
  pX.fillStyle='#080c14';pX.fillRect(0,0,W,H);

  const cols=Math.min(nH,4);
  const rows=Math.ceil(nH/cols);
  const cellW=W/cols,cellH=H/rows;

  for(let i=0;i<nH;i++){
    const n=harmType==='odd'?(2*i+1):(i+1);
    const r=(ampPx/n)*ampScale;
    const cx=cellW*(i%cols)+cellW/2;
    const cy=cellH*Math.floor(i/cols)+cellH/2;
    const angle=t*n;

    pX.strokeStyle='rgba(255,255,255,0.06)';pX.lineWidth=0.5;
    pX.beginPath();pX.arc(cx,cy,r,0,Math.PI*2);pX.stroke();

    const color=n===1?'#378ADD':(n%2===0?'#5DCAA5':'#EF9F27');
    const ex=cx+r*Math.cos(angle),ey=cy+r*Math.sin(angle);

    pX.strokeStyle=color+'66';pX.lineWidth=1;
    pX.beginPath();pX.arc(cx,cy,r,0,Math.PI*2);pX.stroke();

    pX.strokeStyle=color;pX.lineWidth=2;
    pX.beginPath();pX.moveTo(cx,cy);pX.lineTo(ex,ey);pX.stroke();

    pX.fillStyle=color;
    pX.beginPath();pX.arc(ex,ey,3.5,0,Math.PI*2);pX.fill();
    pX.beginPath();pX.arc(cx,cy,2.5,0,Math.PI*2);pX.fill();

    pX.fillStyle='rgba(180,210,240,0.55)';pX.font='10px sans-serif';pX.textAlign='center';
    pX.fillText('n='+n,cx,cy-r-5);
    pX.textAlign='left';
  }
}

function buildHarmBars(){
  const harmBars=document.getElementById('harmBars');
  harmBars.innerHTML='';
  const nH=parseInt(harmInput.value);
  const amps=getAmps(nH,harmType,1);
  amps.forEach(({n,a})=>{
    const b=document.createElement('div');
    b.className='hb';b.style.flex='1';
    b.style.height=Math.max(2,a/amps[0].a*26)+'px';
    b.style.background=n===1?'#378ADD':(n%2===0?'#5DCAA5':'#EF9F27');
    harmBars.appendChild(b);
  });
}

function calcTHD(){
  const nH=parseInt(harmInput.value);
  const ampPx=parseInt(ampInput.value)/100;
  const threshold=parseInt(clipLvl.value)/100;
  const amps=getAmps(nH,harmType,ampPx);
  let sumSq=0;
  for(let i=1;i<amps.length;i++) sumSq+=amps[i].a*amps[i].a;
  let thd=(Math.sqrt(sumSq)/(amps[0].a||1))*100;
  if(isClipping&&ampPx>threshold){thd+=(ampPx-threshold)/ampPx*80;}
  thd=Math.min(thd,130);
  const el=document.getElementById('mT');
  el.textContent=thd.toFixed(2)+'%';
  el.className='met-val '+(thd>30?'bad':thd>5?'warn':'ok');
  const waveNames=['Чистый синус','Мягкий тембр','Насыщенный','Пилообразная'];
  const wi=nH===1?0:nH<=3?1:nH<=8?2:3;
  const wn=harmType==='odd'?(nH>5?'Меандр':'Квазимеандр'):waveNames[wi];
  document.getElementById('mW').textContent=wn;
  document.getElementById('bdWave').textContent=wn;
}

let lastT=0;
function loop(ts=0){
  if(!isPlaying){raf=null;return;}
  const dt=(ts-lastT)/1000||0;lastT=ts;
  const spd=parseInt(speedInput.value);
  phase+=dt*spd*0.8;
  drawWave(phase);
  drawSpec(phase);
  drawPhasor(phase);
  buildHarmBars();
  calcTHD();
  updateLabels();
  raf=requestAnimationFrame(loop);
}

loop();
</script>
</body>
</html>
