<script>

  import { onMount } from 'svelte';
  
  
  onMount(()=> {
    let mycanvas = document.getElementById("mycanvas");
    let ctx = mycanvas.getContext('2d');
    let drawingMode = false; // true 일때만 그리게 됨
    let brush = 'color'; // 'color','image'
    let control = document.querySelector('.control');
    let colorValue = 'black';

    const imgElem = new Image();
    imgElem.src = '../images/touch-icons/logo-192.png';


    function setColor(e) {
      brush =  e.target.getAttribute('data-type');
      console.log(e.target.getAttribute('data-color'));
      colorValue = e.target.getAttribute('data-color');
      ctx.fillStyle = colorValue ;
      console.log(brush)
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

      switch (brush){
        case 'color' :
          ctx.beginPath();
          ctx.arc(e.layerX, e.layerY, 5, 0, Math.PI*2, false);
          ctx.fill();
          break;
        case 'image':
          ctx.drawImage(imgElem, e.layerX, e.layerY, 50, 50);
          break;
      }

      console.log(e);
      console.log(e.clientY);
      console.log(e.layerY);
    }

    mycanvas.addEventListener('mousedown', downHandler);
    mycanvas.addEventListener('mousemove', moveHandler);
    mycanvas.addEventListener('mouseup', upHandler);
    control.addEventListener('click', setColor);
  })
  </script>
  
  <h2 class="title">그리기 앱 ( 색상 대신 image 그리기 추가) </h2>
  <span class="date">2021-03-08</span>
  <p class="description">
    let brush에 image일때 color일때를 넣어주고 값에따라 핸들링한다.
  </p>
  
  <div class="control">
    <button class="color-btn" data-type="color" data-color="black"></button>
    <button class="color-btn" data-type="color" data-color="red"></button>
    <button class="color-btn" data-type="color" data-color="blue"></button>
    <button class="color-btn" data-type="color" data-color="green"></button>
    <button class="image-btn" data-type="image" ></button>
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
      .image-btn {
        width: 40px;
        height: 40px;
        background: url(../images/touch-icons/logo-192.png) no-repeat 50% 50% / cover;

      }
  </style>
  