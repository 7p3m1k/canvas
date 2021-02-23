<script>
  import { onMount } from 'svelte';


  onMount(()=> {
    let myCanvas = document.getElementById("myCanvas");
    let ctx = myCanvas.getContext('2d');

    let xPos = 10;

    function draw() {
      ctx.clearRect(0, 0, myCanvas.width, myCanvas.height);
      ctx.beginPath();
      ctx.arc(xPos, 150, 10, 0, Math.PI*2 );    //360도는 2파이
      ctx.fill();
      xPos += 1 ;

      // console.log('draw');
      requestAnimationFrame(draw);
    }
    draw();
  })

  </script>


<h2 class="title">requestAnimationFrame</h2>
<span class="date">2021-02-23</span>
<p class="description">
  캔버스 애니메이션은 만들고 지우고를 반복해서 움직이는것처럼 보이게 하는것 <br/>
  함수안에 requestAnimationFrame()를 넣고 requestAnimationFrame() 첫번째 매개변수에 인자로 그릴 함수를 넣어주면 반복 실행하게된다.

</p>


<canvas id="myCanvas" width="500" height="300"></canvas>


<style>
  @import url("./canvasText.css");

  canvas {
    background-color: #eee;
  }
</style>