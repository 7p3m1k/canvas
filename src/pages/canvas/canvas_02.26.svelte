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
      ctx.fillRect(xPos, 100, 150 ,150 );    //360도는 2파이    //360도는 2파이
      ctx.fill();
      xPos += 1 ;

      // if (xPos >= myCanvas.width-10) {  //width에 -10준 이유는 원의 크기만큼 빼서 딱 닿으면 멈추게 하기위해서
      //   return;
      // }
      timerId = requestAnimationFrame(draw);
      myCanvas.addEventListener('click', ()=> { cancelAnimationFrame(timerId); });

    }
    draw();
  })

  onMount(()=> {
    let myCanvas2 = document.getElementById("myCanvas2");
    let ctx2 = myCanvas2.getContext('2d');

    let xPos = 10;
    let timerId;

    function draw2() {
      ctx2.clearRect(0, 0, myCanvas2.width, myCanvas2.height);
      ctx2.beginPath();
      ctx2.fillRect(xPos, 100, 150 ,150 );    //360도는 2파이
      ctx2.fill();
      xPos += 5 ;
    }
    timerId = setInterval(draw2, 96);

    myCanvas2.addEventListener('click', ()=> { clearInterval(timerId); });
  })

</script>


<h2 class="title">requestAnimationFrame,setInterval 멈추게하기 2가지 방법 </h2>
<span class="date">2021-02-26</span>
<p class="description">
  애니메이션을 멈추게 하는방법 2가지<br/>
  addEventListener 넣어줬다 캔버스 클릭하면 멈춤 !!

</p>


<canvas id="myCanvas" width="500" height="300"></canvas>
<canvas id="myCanvas2" width="500" height="300"></canvas>

<style>
  @import url("./canvasText.css");

  canvas {
    background-color: #eee;
  }
</style>