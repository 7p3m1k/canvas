<script>

  import { onMount } from 'svelte';
  
  onMount(()=> {
    let mycanvas = document.getElementById("mycanvas");
    let ctx = mycanvas.getContext('2d');
    let drawingMode = false; // true 일때만 그리게 됨

    function downHandler(){
      drawingMode = true;
    }


    function upHandler(){
      drawingMode = false;
    }


    function clickHandler(e){
      if (!drawingMode)
      return;
      console.log(e);
      console.log(e.clientY);
      console.log(e.layerY);
      ctx.fillStyle="yellow";
      ctx.beginPath();
      ctx.arc(e.layerX, e.layerY, 10, 0, Math.PI*2, false);
      ctx.fill();
    }

    mycanvas.addEventListener('mousedown', downHandler);
    mycanvas.addEventListener('mousemove', clickHandler);
    mycanvas.addEventListener('mouseup', upHandler);
  })
  </script>
  
  <h2 class="title">그리기 앱 </h2>
  <span class="date">2021-03-04</span>
  <p class="description">
    mousedown,mousemove,mouseup 을 이용하여 그림을 그릴 수 있게 만들었다. <br/>
    mousedown,mouseup을 할시 drawingMode값을 true false로 변경하여 mousemove를 조작한다.
  </p>
  
  <canvas id="mycanvas" width="600" height="400"></canvas>
  
  
  <style>
      @import url("./canvasText.css");

      #mycanvas {
        background-color: gray;
      }
  </style>
  