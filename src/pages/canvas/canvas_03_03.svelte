<script>

  import { onMount } from 'svelte';
  
  onMount(()=> {
    let mycanvas = document.getElementById("mycanvas");
    let ctx = mycanvas.getContext('2d');

    function clickHandler(e){
      console.log(e);
      console.log(e.clientY);
      console.log(e.layerY);
      ctx.beginPath();
      ctx.arc(e.layerX, e.layerY, 10, 0, Math.PI*2, false);
      ctx.fill();
    }

    mycanvas.addEventListener('click', clickHandler);
  })
  </script>
  
  <h2 class="title">그림판 원하는 위치에 원찍기</h2>
  <span class="date">2021-03-03</span>
  <p class="description">
    clientY , clientX는 브라우저 왼쪽 기준으로 잡는다. <br/>
    layerY , layerX는 캔버스 위치 기준으로 잡힌다. (console.log()찍어봄) <br/>
    그럼 layer를 x,y값에 넣어주면 해당 위치에 원하는 도형을 찍을수있다.
  </p>
  
  <canvas id="mycanvas" width="600" height="400"></canvas>
  
  
  <style>
      @import url("./canvasText.css");

      #mycanvas {
        background-color: gray;
      }
  </style>
  