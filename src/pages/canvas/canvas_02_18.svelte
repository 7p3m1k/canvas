<script>
  import { onMount } from 'svelte';



  function 라디안(각도){
    return 각도 * Math.PI / 180;
  }


  onMount(()=> {
    let myCanvas = document.getElementById("myCanvas");
    let ctx = myCanvas.getContext('2d');

    ctx.beginPath();
    ctx.arc(300, 200, 50, 0, 라디안(360), false);
    ctx.stroke();

    ctx.beginPath();
    ctx.arc(323, 200, 25, 0, 라디안(180), true);
    ctx.stroke();

    ctx.beginPath();
    ctx.arc(273, 200, 25, 0, 라디안(180), false);
    ctx.stroke();
  })

  </script>


<h2 class="title">태극마크</h2>
<span class="date">2021-02-18</span>
<p class="description">
  일단은...이렇게 해봤는데... 다음에는 색도 넣는법 찾아봐야겠다..<br/>
  arc는 좌표를 중심으로 그려진다.
</p>


<canvas id="myCanvas" width="600" height="400"></canvas>


<style>
  @import url("./canvasText.css");

  canvas {
    background-color: #eee;
  }
</style>