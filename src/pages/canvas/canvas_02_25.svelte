<script>
  import { onMount } from 'svelte';


  onMount(()=> {
    let myCanvas = document.getElementById("myCanvas");
    let ctx = myCanvas.getContext('2d');

    let xPos = 10;
    let timerId;

    function draw() {
      ctx.clearRect(0, 0, myCanvas.width, myCanvas.height);
      ctx.beginPath();
      ctx.arc(xPos, 150, 10, 0, Math.PI*2 );    //360도는 2파이
      ctx.fill();
      xPos += 1 ;

      // if (xPos >= myCanvas.width-10) {  //width에 -10준 이유는 원의 크기만큼 빼서 딱 닿으면 멈추게 하기위해서
      //   return;
      // }

      timerId = requestAnimationFrame(draw);
      
      if (xPos >= myCanvas.width-10) {  //width에 -10준 이유는 원의 크기만큼 빼서 딱 닿으면 멈추게 하기위해서
        cancelAnimationFrame(timerId);
      }

    }
    draw();
  })

  </script>


<h2 class="title">requestAnimationFrame 멈추게하기 </h2>
<span class="date">2021-02-25</span>
<p class="description">
  애니메이션을 멈추게 하는방법 2가지<br/>
  1. requestAnimationFrame를 실행하기전에 if문으로 return 하기 <br/>
  2. requestAnimationFrame를 timerId변수에 담아서 cancelAnimationFrame 사용하여 멈추기

</p>


<canvas id="myCanvas" width="500" height="300"></canvas>


<style>
  @import url("./canvasText.css");

  canvas {
    background-color: #eee;
  }
</style>