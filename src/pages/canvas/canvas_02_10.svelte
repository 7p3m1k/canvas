<script>
  import { onMount } from 'svelte';
  
  onMount(()=> {
    let myCanvas = document.getElementById("myCanvas");
    let ctx = myCanvas.getContext('2d');

    for (var i = 0; i < 6; i++) {
      for (var j = 0; j < 6; j++) {
        ctx.strokeStyle = 'rgb(0, ' + Math.floor(255 - 42.5 * i) + ', ' +
                         Math.floor(255 - 42.5 * j) + ')';
        ctx.beginPath();
        ctx.arc(12.5 + j * 25, 12.5 + i * 25, 10, 0, Math.PI * 2, true);
        ctx.stroke();
      }
    }
  })
  </script>
  
  <h2 class="title">strokeStyle예</h2>
  <span class="date">2021-02-10</span>
  <p class="description">
    strokeStyle속성을 사용 하여 모양의 윤곽선 색상을 변경합니다. 우리 arc()는 사각형 대신 원을 그리는 방법을 사용합니다 .
  </p>
  
  <canvas id="myCanvas" width="1000" height="600"></canvas>
  
  
  <style>
      @import url("./canvasText.css");
  </style>
  