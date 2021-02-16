<script>
  import { onMount } from 'svelte';
  
  onMount(()=> {
    let myCanvas = document.getElementById("myCanvas");
    let ctx = myCanvas.getContext('2d');

    let offset = 0;

  function draw() {
    ctx.clearRect(0, 0, myCanvas.width, myCanvas.height);
    ctx.setLineDash([4, 2]);
    ctx.lineDashOffset = -offset;
    ctx.strokeRect(10, 10, 100, 100);
  }

  function march() {
    offset++;
    if (offset > 16) {
      offset = 0;
    }
    draw();
    setTimeout(march, 20);
  }
  march();
  })

  </script>
  
  <h2 class="title">라인 대시 사용</h2>
  <span class="date">2021-02-16</span>
  <p class="description">
    <strong>setLineDash</strong>방법과 <strong>lineDashOffset</strong> 선의 대시 패턴을 지정.<br/>
    setLineDash메서드는 선과 간격을 교대로 그리는 거리를 지정하는 숫자 목록을 받아들이고<br/>
    lineDashOffset속성은 패턴을 시작할 오프셋을 설정.<br/>
  </p>
  
  <canvas id="myCanvas" width="1000" height="600"></canvas>
  
  
  <style>
      @import url("./canvasText.css");
  </style>
  