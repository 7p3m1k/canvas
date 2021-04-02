<script>
  import { onMount } from 'svelte';
  
  onMount(()=> {
    let Canvas = document.getElementById("Canvas");
    let ctx = Canvas.getContext('2d');

    let joinType=['bevel','round','miter'];
    ctx.strokeStyle='black';
    for(let i=0;i<joinType.length;i++){
      ctx.lineJoin = joinType[i];
      ctx.lineWidth=20;
      ctx.beginPath();
      ctx.moveTo(25,5+i*70);
      ctx.lineTo(35,45+i*70);
      ctx.lineTo(75,5+i*70);
      ctx.lineTo(115,45+i*70);
      ctx.lineTo(155,5+i*70);
      ctx.stroke();
    }
  })

  </script>
  
  <h2 class="title">선 연결 모양</h2>
  <span class="date">2021-04-01</span>
  <p class="description">
    lineJoin = [ joinType ] // 선의 꺽인 부분의 타입을 지정한다. [round, bevel, miter]가 있다.
    </p>
  <div>
    <canvas id="Canvas" width="1000" height="300"></canvas>
  </div>
  <style>
      @import url("./canvasText.css");


  </style>
