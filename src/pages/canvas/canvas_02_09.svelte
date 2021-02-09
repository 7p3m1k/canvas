<script>
  import { onMount } from 'svelte';
  
  onMount(()=> {
    let myCanvas = document.getElementById("myCanvas");
    let ctx = myCanvas.getContext('2d');

    for (var i = 0; i < 6; i++) {
      for (var j = 0; j < 6; j++) {
        ctx.fillStyle = 'rgb(' + Math.floor(255 - 42.5 * i) + ', ' +
                        Math.floor(255 - 42.5 * j) + ', 0)';
        ctx.fillRect(j * 25, i * 25, 25, 25);
      }
    }
  })
  </script>
  
  <h2 class="title">fillStyle 예</h2>
  <span class="date">2021-02-09</span>
  <p class="description">
    모양에 색상을 적용하려는 경우 사용할 수있는 두 가지 중요한 속성이 있습니다. fillStyle및 strokeStyle.<br/>
    fillStyle = color<br/>
    도형을 채울 때 사용되는 스타일을 설정합니다. <br/>
    strokeStyle = color<br/>
    도형의 외곽선 스타일을 설정합니다.<br/>
  </p>
  
  <canvas id="myCanvas" width="1000" height="600"></canvas>
  
  
  <style>
      @import url("./canvasText.css");
  </style>
  