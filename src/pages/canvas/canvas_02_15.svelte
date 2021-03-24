<script>
  import { onMount } from 'svelte';
  
  onMount(()=> {
    let myCanvas = document.getElementById("myCanvas");
    let ctx = myCanvas.getContext('2d');
    let lineCap = ['butt', 'round', 'square'];

    // Draw guides
    ctx.strokeStyle = '#09f';
    ctx.beginPath();
    ctx.moveTo(10, 10);
    ctx.lineTo(140, 10);
    ctx.moveTo(10, 140);
    ctx.lineTo(140, 140);
    ctx.stroke();

    // Draw lines
    ctx.strokeStyle = 'black';
    for (let i = 0; i < lineCap.length; i++) {
      ctx.lineWidth = 15;
      ctx.lineCap = lineCap[i];
      ctx.beginPath();
      ctx.moveTo(25 + i * 50, 10);
      ctx.lineTo(25 + i * 50, 140);
      ctx.stroke();
    }
  })

  onMount(()=> {
    let ctx = document.getElementById('canvas').getContext('2d');
    let lineJoin = ['round', 'bevel', 'miter'];
    ctx.lineWidth = 10;
    for (let i = 0; i < lineJoin.length; i++) {
      ctx.lineJoin = lineJoin[i];
      ctx.beginPath();
      ctx.moveTo(-5, 5 + i * 40);
      ctx.lineTo(35, 45 + i * 40);
      ctx.lineTo(75, 5 + i * 40);
      ctx.lineTo(115, 45 + i * 40);
      ctx.lineTo(155, 5 + i * 40);
      ctx.stroke();
    }
  })

  onMount(()=> {
    let c = document.getElementById("canvas3");
    let ctx = c.getContext("2d");
    ctx.beginPath();
    ctx.lineJoin = "round";
    ctx.lineWidth=10;
    ctx.moveTo(20, 20);
    ctx.lineTo(100, 50);
    ctx.lineTo(20, 100);
    ctx.stroke();
  })

  onMount(()=> {
    let cd = document.getElementById("canvas4");
    let ctx = cd.getContext("2d");
    ctx.beginPath();
    ctx.lineJoin = "bevel";
    ctx.lineWidth=10;
    ctx.moveTo(20, 20);
    ctx.lineTo(100, 50);
    ctx.lineTo(20, 100);
    ctx.stroke();
  })

  onMount(()=> {
    let ce = document.getElementById("canvas5");
    let ctx = ce.getContext("2d");
    ctx.beginPath();
    ctx.lineWidth=10;
    ctx.lineJoin = "miter";
    ctx.moveTo(20, 20);
    ctx.lineTo(100, 50);
    ctx.lineTo(20, 100);
    ctx.stroke();
  })

  </script>
  
  <h2 class="title">선 스타일 2</h2>
  <span class="date">2021-02-15</span>
  <h1>lineCap예</h1>
  <p class="description">lineCap속성은 각 줄의 끝 지점이 그려진다.<br/>
    이 속성에는 세 가지 가능한 값이 있으며 butt, round및 square.</p>
  <h3>기본 속성은 (butt).</h3>

  <canvas id="myCanvas" width="1000" height="150"></canvas>
  <h4>왼쪽 부터 'butt', 'round', 'square' 이다. </h4>

  <h1>lineJoin예</h1>
  <p class="description">
    <strong>round : </strong>
    도형의 모서리를, 연결되는 부분들의 공통 끝점을 중심으로 하는 원 모양으로 만듭니다. 
    이때 원의 반지름은 선의 두께와 같습니다.<br/>
    <strong>bevel : </strong>
    도형의 모서리를, 연결되는 부분들의 공통 끝점에서 세모 모양으로 만듭니다.<br/>
    <strong>miter : </strong>
    도형의 모서리를, 두 부분의 바깥쪽 테두리 선을 각각 연장하여 교차된 점으로 생긴 마름모꼴 모양으로 만듭니다. 
    miterLimit 속성값에 따라 모양이 달라집니다.
  </p>
  <h3>기본 속성은 (miter)</h3>
  <div>
    <canvas id="canvas" width="1000" height="300"></canvas>
  </div>

    <canvas id="canvas3" width="200" height="100"></canvas>
    <canvas id="canvas4" width="200" height="100"></canvas>
    <canvas id="canvas5" width="200" height="100"></canvas>
    왼쪽부터 round,bevel,miter 순 (뭐가 다른거지?...)<br/>
    모서리가 다르네 !!

  <style>
      @import url("./canvasText.css");

      h4 {
        margin-bottom: 100px;
      }
  </style>
