<script>

  import { onMount } from 'svelte';
  
  
  onMount(()=> {
    let mycanvas = document.getElementById("mycanvas");
    let ctx = mycanvas.getContext('2d');
    let drawingMode = false; // true 일때만 그리게 됨
    let control = document.querySelector('.control');
    let colorValue = 'black';

    function setColor(e) {
      console.log(e.target.getAttribute('data-color'));
      colorValue = e.target.getAttribute('data-color');
      ctx.fillStyle = colorValue ;
    }


    function downHandler() {
      drawingMode = true;
    }


    function upHandler() {
      drawingMode = false;
    }


    function moveHandler(e) {
      if (!drawingMode)
      return;
      console.log(e);
      console.log(e.clientY);
      console.log(e.layerY);
      ctx.beginPath();
      ctx.arc(e.layerX, e.layerY, 5, 0, Math.PI*2, false);
      ctx.fill();
    }

    mycanvas.addEventListener('mousedown', downHandler);
    mycanvas.addEventListener('mousemove', moveHandler);
    mycanvas.addEventListener('mouseup', upHandler);
    control.addEventListener('click', setColor);
  })
  </script>
  
  <h2 class="title">그리기 앱 ( 선 색상 변경 버튼) </h2>
  <span class="date">2021-03-05</span>
  <p class="description">
    
  </p>
  
  <div class="control">
    <button class="color-btn" data-color="black"></button>
    <button class="color-btn" data-color="red"></button>
    <button class="color-btn" data-color="blue"></button>
    <button class="color-btn" data-color="green"></button>
  </div>
  <canvas id="mycanvas" width="600" height="400"></canvas>
  
  
  <style lang="scss">
      @import url("./canvasText.css");

      #mycanvas {
        background-color: whitesmoke;
        border: 1px solid black;
      }

      .color-btn {
        width: 30px;
        height: 30px;
        border: 0;
        border-radius: 50%;
      }

      .color-btn[data-color="black"] {
        background-color: black;
      }
      .color-btn[data-color="red"] {
        background-color: red;
      }
      .color-btn[data-color="blue"] {
        background-color: blue;
      }
      .color-btn[data-color="green"] {
        background-color: green;
      }
  </style>
  