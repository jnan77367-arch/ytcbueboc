<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
<title>一集一纪 · 遗我回音</title>
<link href="https://fonts.googleapis.com/css2?family=Ma+Shan+Zheng&family=Zhi+Mang+Xing&family=Liu+Jian+Mao+Cao&family=Long+Cang&family=ZCOOL+XiaoWei&display=swap" rel="stylesheet">
<style>
:root { --h1-size: 22px; --btn-blue: #007aff; --btn-active: #ffb900; }
.f-1 { --font-main: 'Ma Shan Zheng'; --h1-size: 30px; }
.f-2 { --font-main: 'Zhi Mang Xing'; --h1-size: 28px; }
.f-3 { --font-main: 'Liu Jian Mao Cao'; --h1-size: 28px; }
.f-4 { --font-main: 'Long Cang'; --h1-size: 28px; }
.f-5 { --font-main: 'ZCOOL XiaoWei'; --h1-size: 24px; }
.f-0 { --font-main: -apple-system, sans-serif; --h1-size: 22px; }

* { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; touch-action: pan-y; }

.bg-layer { position: fixed; top: 0; left: 0; width: 100%; height: 100%; z-index: -3; background: #f0f4f5; transition: 0.8s; }
#wallCanvas { position: fixed; top: 0; left: 0; width: 100%; height: 100%; z-index: -2; pointer-events: none; opacity: 0; transition: 0.5s; }

body { font-family: var(--font-main, -apple-system, sans-serif); color: #2c3e50; min-height: 100vh; overflow-x: hidden; -webkit-text-size-adjust: 100%; }
.container { width: 100%; max-width: 500px; margin: 0 auto; padding: 30px 16px 120px; }

/* 统一透明质感 */
input, .item-wrapper, #logPanel { 
    border-radius: 16px; border: none; background: rgba(255, 255, 255, 0.45); 
    outline: none; font-family: inherit; font-size: 16px; /* 16px防止iOS自动放大 */
}

.item-wrapper { position: relative; margin-bottom: 12px; overflow: hidden; transition: opacity 0.3s; }
.scroll-content { display: flex; width: calc(100% + 85px); transform: translateX(0); will-change: transform; }
.anime-item { width: calc(100% - 85px); padding: 18px; flex-shrink: 0; }
.delete-btn { width: 85px; background: rgba(255, 59, 48, 0.9); color: #fff; display: flex; align-items: center; justify-content: center; font-weight: bold; }

.btn-ui { padding: 12px 10px; border: none; border-radius: 14px; background: var(--btn-blue); color: #fff; font-weight: bold; font-size: 14px; cursor: pointer; }
.log-on { background: var(--btn-active) !important; color: #000 !important; }

#logPanel { display:none; padding:15px; margin-bottom: 15px; font-size: 13px; max-height: 200px; overflow-y: auto; }
#eggPanel { position: fixed; inset: 0; background: #000; z-index: 10000; display: none; flex-direction: column; align-items: center; justify-content: center; color: #fff; }
</style>
</head>
<body class="f-0">

<div class="bg-layer" id="bgLayer"></div>
<canvas id="wallCanvas"></canvas>

<div class="container">
    <div class="title-wrap" id="titleHead" style="height: 80px; display: flex; align-items:center; justify-content:center; cursor:pointer;">
        <h1 class="main-title" id="displayTitle">动漫追番进度</h1>
    </div>
    
    <input type="text" id="searchBar" placeholder="🔍 输入番名，即刻寻觅..." style="width:100%; margin-bottom:12px; padding: 12px;">
    
    <div style="display:flex; gap:8px; margin-bottom:15px;">
        <input type="text" id="name" placeholder="刻下番名..." style="flex:1; padding: 12px;">
        <button class="btn-ui" id="addBtn" style="padding: 0 20px;">添加</button>
    </div>

    <div style="display:grid; grid-template-columns: 1fr 1fr 1fr; gap:10px; margin-bottom: 25px;">
        <button class="btn-ui" id="logBtn">日志</button>
        <button class="btn-ui" id="bgBtn" style="display:none;">背景</button>
        <button class="btn-ui" id="colorBtn" style="display:none;">变色</button>
    </div>

    <div id="logPanel"><div id="logList"></div></div>
    <div id="list"></div>
</div>

<input type="file" id="fileInput" accept="image/*" style="display:none;">

<div id="eggPanel">
    <div style="font-family:'Ma Shan Zheng'; font-size:28px; margin-bottom:30px; letter-spacing:4px;">此间留白，独我知情</div>
    <div style="font-size: 50px; margin-bottom: 20px;">🐲</div>
    <button onclick="confirmUnlock()" style="padding: 15px 50px; border-radius: 30px; border: 1px solid #d4af37; background: transparent; color: #d4af37; font-weight: bold;">入 画</button>
</div>

<script>
const grads = ['linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%)','linear-gradient(135deg, #e0c3fc 0%, #8ec5fc 100%)','linear-gradient(135deg, #f093fb 0%, #f5576c 100%)','linear-gradient(135deg, #fdfcfb 0%, #e2d1c3 100%)','linear-gradient(135deg, #a8edea 0%, #fed6e3 100%)','linear-gradient(135deg, #d299c2 0%, #fef9d7 100%)','linear-gradient(135deg, #ebedee 0%, #fdfbfb 100%)','linear-gradient(135deg, #accbee 0%, #e7f0fd 100%)','linear-gradient(135deg, #e1eec3 0%, #f05053 100%)','linear-gradient(135deg, #f5f5f5 0%, #c0c0c0 100%)','linear-gradient(225deg, #FF3CAC 0%, #784BA0 50%, #2B86C5 100%)','linear-gradient(160deg, #0093E9 0%, #80D0C7 100%)','linear-gradient(45deg, #85FFBD 0%, #FFFB7D 100%)','linear-gradient(62deg, #8EC5FC 0%, #E0C3FC 100%)','linear-gradient(132deg, #F4D03F 0%, #16A085 100%)','linear-gradient(180deg, #FFFFFF 0%, #6284FF 50%, #FF0000 100%)','linear-gradient(0deg, #FFDEE9 0%, #B5FFFC 100%)','linear-gradient(90deg, #74EBD5 0%, #9FACE6 100%)','linear-gradient(45deg, #FBDA61 0%, #FF5ACD 100%)','linear-gradient(19deg, #21D4FD 0%, #B721FF 100%)','linear-gradient(147deg, #FFE53B 0%, #FF2525 74%)','linear-gradient(43deg, #4158D0 0%, #C850C0 46%, #FFCC70 100%)','linear-gradient(135deg, #667eea 0%, #764ba2 100%)','linear-gradient(to top, #cfd9df 0%, #e2ebf0 100%)','linear-gradient(to top, #a18cd1 0%, #fbc2eb 100%)','linear-gradient(to right, #ff8177 0%, #ff867a 0%, #ff8c7f 21%, #f99185 52%, #cf8e81 78%, #b12a5b 100%)','linear-gradient(to top, #d5d4d0 0%, #d5d4d0 1%, #eeeeec 31%, #efeeec 75%, #e9e9e7 100%)','linear-gradient(to top, #5f72bd 0%, #9b23ea 100%)','linear-gradient(to top, #09203f 0%, #537895 100%)','linear-gradient(120deg, #84fab0 0%, #8fd3f4 100%)'];

const bgLayer = document.getElementById('bgLayer');
const wallCanvas = document.getElementById('wallCanvas');
const logList = document.getElementById('logList');
const list = document.getElementById('list');
const searchBar = document.getElementById('searchBar');

// 搜索功能实现
searchBar.addEventListener('input', (e) => {
    const term = e.target.value.toLowerCase();
    const items = list.querySelectorAll('.item-wrapper');
    items.forEach(item => {
        const title = item.querySelector('.anime-title').innerText.toLowerCase();
        item.style.display = title.includes(term) ? 'block' : 'none';
    });
});

// 改进版签名墙：格点化排布，防止重叠成块
function drawArtWall() {
    const ctx = wallCanvas.getContext('2d');
    const w = wallCanvas.width = window.innerWidth;
    const h = wallCanvas.height = window.innerHeight;
    const fonts = ['Ma Shan Zheng', 'Zhi Mang Xing', 'Liu Jian Mao Cao', 'Long Cang'];
    
    const gridSize = 80; // 格子大小
    for(let x = 0; x < w; x += gridSize) {
        for(let y = 0; y < h; y += gridSize) {
            if(Math.random() > 0.7) continue; // 随机留白，更自然
            ctx.save();
            ctx.font = `${Math.random()*15 + 20}px ${fonts[Math.floor(Math.random()*fonts.length)]}`;
            ctx.fillStyle = `rgba(0,0,0,${Math.random()*0.12 + 0.05})`;
            // 在格子里微调位置，防止死板
            const posX = x + Math.random() * (gridSize/2);
            const posY = y + Math.random() * (gridSize/2);
            ctx.translate(posX, posY);
            ctx.rotate((Math.random() - 0.5) * 0.8); // 旋转角度控制在一定范围
            ctx.fillText('寶鎍', 0, 0);
            ctx.restore();
        }
    }
}

function addItem(title, status='连载', day='周一', ep='1', h='00', m='00', isLoad=false) {
    const wrap = document.createElement('div');
    wrap.className = 'item-wrapper';
    wrap.innerHTML = `<div class="scroll-content"><div class="anime-item"><div class="anime-title" style="font-weight:bold; margin-bottom:8px;">${title}</div><div style="display:flex; gap:5px; align-items:center;"><select class="status-select" style="background:transparent;"><option ${status=='连载'?'selected':''}>连载</option><option ${status=='完结'?'selected':''}>完结</option></select><select class="day-select" style="background:transparent;">${['周一','周二','周三','周四','周五','周六','周日'].map(d=>`<option ${day==d?'selected':''}>${d}</option>`).join('')}</select><input type="number" class="ep-input" value="${ep}" style="width:40px; background:transparent;"> <span>集</span><input type="number" class="h-in" value="${h}" style="width:35px; background:transparent;"><b>:</b><input type="number" class="m-in" value="${m}" style="width:35px; background:transparent;"></div></div><div class="delete-btn">斩断</div></div>`;
    list.prepend(wrap);

    const sc = wrap.querySelector('.scroll-content');
    let startX = 0, startY = 0, currentX = 0, lock = false;

    wrap.addEventListener('touchstart', e => {
        startX = e.touches[0].clientX; startY = e.touches[0].clientY;
        sc.style.transition = 'none'; lock = false;
    }, {passive:true});

    wrap.addEventListener('touchmove', e => {
        let diffX = e.touches[0].clientX - startX;
        let diffY = e.touches[0].clientY - startY;
        if(!lock && Math.abs(diffY) > Math.abs(diffX)) { lock = true; return; }
        if(lock) return;
        if(diffX < 0) { currentX = Math.max(diffX, -85); sc.style.transform = `translateX(${currentX}px)`; }
        else if(diffX > 0 && currentX < 0) { currentX = Math.min(diffX - 85, 0); sc.style.transform = `translateX(${currentX}px)`; }
    }, {passive:true});

    wrap.addEventListener('touchend', () => {
        sc.style.transition = 'transform 0.3s cubic-bezier(0.18, 0.89, 0.32, 1)';
        currentX = (currentX < -40) ? -85 : 0;
        sc.style.transform = `translateX(${currentX}px)`;
    });

    wrap.querySelector('.delete-btn').onclick = () => {
        addLog(`已斩断番缘：${title} (止于第 ${wrap.querySelector('.ep-input').value} 集)`);
        wrap.remove(); save();
    };
    wrap.querySelectorAll('select, input').forEach(i => i.onchange = save);
    if(!isLoad) save();
}

function addLog(msg, isSave = true) {
    const t = new Date().toLocaleTimeString([], {hour:'2-digit', minute:'2-digit'});
    const entry = `[${t}] ${msg}`;
    const d = document.createElement('div'); d.style.padding = "4px 0"; d.innerText = entry;
    logList.prepend(d);
    if(isSave) {
        let logs = JSON.parse(localStorage.getItem('logs_v28') || '[]');
        logs.unshift(entry); localStorage.setItem('logs_v28', JSON.stringify(logs.slice(0, 50)));
    }
}

function save() {
    const data = [...list.querySelectorAll('.item-wrapper')].map(el => ({
        title: el.querySelector('.anime-title').innerText, status: el.querySelector('.status-select').value,
        day: el.querySelector('.day-select').value, ep: el.querySelector('.ep-input').value,
        h: el.querySelector('.h-in').value, m: el.querySelector('.m-in').value
    }));
    localStorage.setItem('anime_v28', JSON.stringify(data));
}

document.getElementById('colorBtn').onclick = () => {
    wallCanvas.style.opacity = '0'; localStorage.removeItem('is_wall_v28');
    let c = grads[Math.floor(Math.random() * grads.length)];
    bgLayer.style.background = c; localStorage.setItem('bg_v28', c);
};

document.getElementById('bgBtn').onclick = () => {
    if(wallCanvas.style.opacity === '0') {
        drawArtWall(); wallCanvas.style.opacity = '1';
        localStorage.setItem('is_wall_v28', 'true');
        addLog("展开清晰签名墙");
    } else { document.getElementById('fileInput').click(); }
};

document.getElementById('fileInput').onchange = (e) => {
    const reader = new FileReader();
    reader.onload = (ev) => {
        wallCanvas.style.opacity = '0';
        bgLayer.style.background = `url(${ev.target.result}) center/cover no-repeat`;
        localStorage.setItem('c_bg_v28', ev.target.result);
        localStorage.removeItem('is_wall_v28');
    };
    reader.readAsDataURL(e.target.files[0]);
};

document.getElementById('logBtn').onclick = function() {
    const p = document.getElementById('logPanel');
    p.style.display = (p.style.display === 'block') ? 'none' : 'block';
    this.classList.toggle('log-on');
};

let clickCount = 0;
document.getElementById('titleHead').onclick = () => {
    if(localStorage.getItem('unlocked_v28') !== 'true') {
        if(++clickCount >= 10) { document.getElementById('eggPanel').style.display='flex'; clickCount=0; }
    } else {
        let fidx = (parseInt(localStorage.getItem('fidx_v28') || 0) + 1) % 6;
        document.body.className = 'f-' + fidx; localStorage.setItem('fidx_v28', fidx);
    }
};

function confirmUnlock() { localStorage.setItem('unlocked_v28', 'true'); location.reload(); }

window.onload = () => {
    if(localStorage.getItem('unlocked_v28') === 'true') {
        document.getElementById('displayTitle').innerText = '一集一纪 遗我回音';
        document.getElementById('colorBtn').style.display = 'block';
        document.getElementById('bgBtn').style.display = 'block';
        document.body.className = 'f-' + (localStorage.getItem('fidx_v28') || 0);
    }
    if(localStorage.getItem('is_wall_v28') === 'true') { drawArtWall(); wallCanvas.style.opacity = '1'; }
    const cbg = localStorage.getItem('c_bg_v28'), b = localStorage.getItem('bg_v28');
    if(cbg) bgLayer.style.background = `url(${cbg}) center/cover no-repeat`; else if(b) bgLayer.style.background = b;
    JSON.parse(localStorage.getItem('anime_v28') || '[]').forEach(d => addItem(d.title, d.status, d.day, d.ep, d.h, d.m, true));
    JSON.parse(localStorage.getItem('logs_v28') || '[]').reverse().forEach(l => {
        const d = document.createElement('div'); d.style.padding = "4px 0"; d.innerText = l; logList.prepend(d);
    });
};

document.getElementById('addBtn').onclick = () => {
    const n = document.getElementById('name').value.trim();
    if(n) { addItem(n); addLog(`新番入列：${n}`); document.getElementById('name').value = ''; }
};
</script>
</body>
</html>
