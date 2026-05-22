<!DOCTYPE html>
<html lang="zh-Hant">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>自製刮刮樂 Pro</title>

<style>

body{
  font-family:sans-serif;
  margin:0;
  background:#111;
  color:white;
}

.container{
  padding:16px;
  max-width:1200px;
  margin:auto;
}

.card{
  background:#1e1e1e;
  padding:16px;
  border-radius:16px;
  margin-bottom:16px;
  box-shadow:0 0 15px rgba(0,0,0,.4);
}

input,select,button{
  width:100%;
  padding:12px;
  margin-top:8px;
  border-radius:10px;
  border:none;
}

button{
  background:#00c853;
  color:white;
  font-weight:bold;
}

.grid{
  display:grid;
  gap:8px;
}

.grid.portrait{
  grid-template-columns:repeat(5,1fr);
}

.grid.landscape{
  grid-template-columns:repeat(10,1fr);
}

/* 🌈 RGB外框 */
.paperFrame{
  padding:12px;
  border-radius:20px;
  background:linear-gradient(
    45deg,
    red,
    orange,
    yellow,
    lime,
    cyan,
    blue,
    violet,
    red
  );
  background-size:400% 400%;
  animation:rgbMove 6s linear infinite;
}

@keyframes rgbMove{
  0%{background-position:0% 50%;}
  100%{background-position:400% 50%;}
}

/* 🖼 刮刮卡背景 */
.paper{
  border-radius:16px;
  padding:12px;
  background-size:cover;
  background-position:center;
  min-height:400px;
}

.slot{
  position:relative;
  width:100%;
  aspect-ratio:1/1;
  overflow:hidden;
  border-radius:12px;
}

.text{
  position:absolute;
  inset:0;
  display:flex;
  align-items:center;
  justify-content:center;
  font-weight:bold;
  z-index:2;
}

canvas{
  position:absolute;
  inset:0;
  z-index:5;
}

.num{
  position:absolute;
  inset:0;
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:24px;
  font-weight:bold;
  color:white;
  z-index:6;
  pointer-events:none;
  text-shadow:0 0 5px black;
}

/* 🎊 彩帶 */
.confetti{
  position:fixed;
  width:10px;
  height:10px;
  top:-20px;
  animation:fall 3s linear forwards;
  z-index:9999;
}

@keyframes fall{
  to{
    transform:translateY(120vh) rotate(720deg);
  }
}

.hidden{
  display:none;
}

</style>
</head>

<body>

<div class="container">

<div id="editor" class="card">

<h2>🎮 自製刮刮樂 Pro</h2>

洞數（10倍數）
<input id="count" type="number" value="20" step="10">

模式
<select id="mode">
<option value="portrait">直向</option>
<option value="landscape">橫向</option>
</select>

獎品內容
<input id="items" placeholder="100,200,A,蘋果">

🎯 中獎號碼（例如 3）
<input id="winNumber" value="3">

📝 刮開文字
<input id="winText" value="中獎！">

🎨 刮開文字顏色
<input id="textColor" type="color" value="#ff0000">

🔤 字體大小
<input id="fontSize" type="number" value="22">

🟨 刮洞底色
<input id="slotColor" type="color" value="#ffffff">

🌈 刮層顏色
<select id="paintColor">
<option value="#ff4d4d">紅</option>
<option value="#4d79ff">藍</option>
<option value="#4dff88">綠</option>
<option value="#ffcc4d">黃</option>
<option value="#b84dff">紫</option>
<option value="#00c2ff">青</option>
<option value="#c0c0c0">銀</option>
<option value="#000000">黑</option>
</select>

🖼 刮刮卡背景
<input id="bgImage" type="file" accept="image/*">

🖼 格子圖片
<input id="images" type="file" multiple accept="image/*">

<button onclick="build()">生成刮刮樂</button>

</div>

<div id="game" class="card hidden">

<h2>🎰 刮刮樂</h2>

<div class="paperFrame">
<div id="paper" class="paper">
<div id="grid" class="grid"></div>
</div>
</div>

<br>

<button onclick="reset()">返回編輯</button>

</div>

</div>

<!-- 🔊 音效 -->
<audio id="scratchSound"
src="https://assets.mixkit.co/active_storage/sfx/212/212-preview.mp3"></audio>

<audio id="winSound"
src="https://assets.mixkit.co/active_storage/sfx/951/951-preview.mp3"></audio>

<script>

let data=[];

function build(){

  let count=+document.getElementById('count').value;

  if(count % 10 !== 0){
    alert("請輸入10的倍數");
    return;
  }

  let mode=document.getElementById('mode').value;
  let items=document.getElementById('items').value.split(',');
  let files=document.getElementById('images').files;

  data=[];

  for(let i=0;i<count;i++){

    data.push({
      text:items[i % items.length] || '',
      img:files[i % files.length]
      ? URL.createObjectURL(files[i % files.length])
      : null
    });

  }

  // 背景圖
  let bg=document.getElementById('bgImage').files[0];

  if(bg){
    document.getElementById('paper').style.backgroundImage=
    `url(${URL.createObjectURL(bg)})`;
  }

  document.getElementById('editor').classList.add('hidden');
  document.getElementById('game').classList.remove('hidden');

  render(mode);

}

function playScratch(){

  let s=document.getElementById('scratchSound');

  s.pause();
  s.currentTime=0.02;

  s.play().catch(()=>{});

}

function playWin(){

  let s=document.getElementById('winSound');

  s.currentTime=0;

  s.play().catch(()=>{});

}

function confetti(){

  for(let i=0;i<120;i++){

    let d=document.createElement('div');

    d.className='confetti';

    d.style.left=Math.random()*100+'vw';

    d.style.background=
    `hsl(${Math.random()*360},100%,50%)`;

    d.style.animationDuration=
    (Math.random()*2+2)+'s';

    document.body.appendChild(d);

    setTimeout(()=>{
      d.remove();
    },4000);

  }

}

function render(mode){

  let grid=document.getElementById('grid');

  grid.innerHTML='';

  grid.className='grid '+mode;

  let winNumber=
  document.getElementById('winNumber').value;

  let winText=
  document.getElementById('winText').value;

  let textColor=
  document.getElementById('textColor').value;

  let fontSize=
  document.getElementById('fontSize').value;

  let slotColor=
  document.getElementById('slotColor').value;

  let paintColor=
  document.getElementById('paintColor').value;

  data.forEach((d,i)=>{

    let div=document.createElement('div');

    div.className='slot';

    div.style.background=slotColor;

    // 圖片
    if(d.img){

      let img=document.createElement('img');

      img.src=d.img;

      img.style.width='100%';
      img.style.height='100%';
      img.style.objectFit='cover';

      div.appendChild(img);

    }

    // 刮開文字
    let t=document.createElement('div');

    t.className='text';

    t.innerText=d.text;

    t.style.color=textColor;

    t.style.fontSize=fontSize+'px';

    div.appendChild(t);

    // 刮層數字
    let num=document.createElement('div');

    num.className='num';

    num.innerText=i+1;

    div.appendChild(num);

    // canvas
    let c=document.createElement('canvas');

    c.width=300;
    c.height=300;

    div.appendChild(c);

    let ctx=c.getContext('2d');

    ctx.fillStyle=paintColor;

    ctx.fillRect(0,0,300,300);

    let down=false;

    function scratch(e){

      if(!down) return;

      playScratch();

      let r=c.getBoundingClientRect();

      let x=
      (e.touches?e.touches[0].clientX:e.clientX)-r.left;

      let y=
      (e.touches?e.touches[0].clientY:e.clientY)-r.top;

      ctx.globalCompositeOperation='destination-out';

      ctx.beginPath();

      ctx.arc(x,y,20,0,Math.PI*2);

      ctx.fill();

      // 同步刮掉數字
      num.style.opacity='0';

      // 中獎判定
      if((i+1)==winNumber){

        let imgData=
        ctx.getImageData(0,0,300,300).data;

        let clear=0;

        for(let j=3;j<imgData.length;j+=4){

          if(imgData[j]===0) clear++;

        }

        let percent=
        clear/(300*300);

        if(percent>0.45 && !div.dataset.win){

          div.dataset.win=true;

          playWin();

          confetti();

        }

      }

    }

    c.addEventListener('mousedown',()=>down=true);
    c.addEventListener('mouseup',()=>down=false);
    c.addEventListener('mouseleave',()=>down=false);
    c.addEventListener('mousemove',scratch);

    c.addEventListener('touchstart',()=>down=true);
    c.addEventListener('touchend',()=>down=false);
    c.addEventListener('touchmove',scratch);

    grid.appendChild(div);

  });

}

function reset(){

  document.getElementById('editor')
  .classList.remove('hidden');

  document.getElementById('game')
  .classList.add('hidden');

}

</script>

</body>
</html>
