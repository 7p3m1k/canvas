<script>
  import { onMount } from 'svelte';


  onMount(()=> {
    let myCanvas = document.getElementById("myCanvas");
    let ctx = myCanvas.getContext('2d');

    let xPos = 10;
    let count = 0;

    function draw() {
      if (count % 30 === 0 ) {
        // console.log(count);
        ctx.clearRect(0, 0, myCanvas.width, myCanvas.height);
        ctx.beginPath();
        ctx.arc(xPos, 150, 10, 0, Math.PI*2 );    //360도는 2파이
        ctx.fill();
        xPos += 5 ;
      }

      count++;
      requestAnimationFrame(draw);
    }
    draw();
  })


  onMount(()=> {
    let myCanvas2 = document.getElementById("myCanvas2");
    let ctx2 = myCanvas2.getContext('2d');

    let xPos = 10;

    function draw2() {
      ctx2.clearRect(0, 0, myCanvas2.width, myCanvas2.height);
      ctx2.beginPath();
      ctx2.arc(xPos, 150, 10, 0, Math.PI*2, false );    //360도는 2파이
      ctx2.fill();
      xPos += 5 ;
    }
    setInterval(draw2, 500);
  })

  </script>


<h2 class="title">requestAnimationFrame 속도 조절, setinterval 속도조절</h2>
<span class="date">2021-02-24</span>
<p class="description">
  requestAnimationFrame는 초당 60 반복을 목표로 하기 때문에 count % 30 === 0 를 하게되면 0.5초 정도가 되는 인터벌이 생기게 된다. <br/>
  setinterval로도 속도 조절을 할수있다.

</p>


<canvas id="myCanvas" width="500" height="300"></canvas>
requestAnimationFrame
<canvas id="myCanvas2" width="500" height="300"></canvas>
setinterval
<style>
  @import url("./canvasText.css");

  canvas {
    background-color: #eee;
  }
</style>