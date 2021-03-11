
<script>
  import { onMount } from 'svelte';

  let canvas;
  let ctx;
  let x = 75;
  let y = 50;
  let WIDTH = 1000;
  let HEIGHT = 500;
  let dragOk = false;
  
  onMount(()=> {

    function rect(x,y,w,h) {
      ctx.beginPath();
      ctx.rect(x,y,w,h);
      ctx.closePath();
      ctx.fill();
    }
  
  function clear() {
    ctx.clearRect(0, 0, WIDTH, HEIGHT);
  }
  
  function init() {
    canvas = document.getElementById("canvas");
    ctx = canvas.getContext("2d");
    return setInterval(draw, 10);
  }
  
  function draw() {
    clear();
    ctx.fillStyle = "black";
    rect(0,0,WIDTH,HEIGHT);
    ctx.fillStyle = "red";
    rect(x - 15, y - 15, 30, 30);
  }
  
  function myMove(e){
    if (dragOk){
      x = e.pageX - canvas.offsetLeft;
      y = e.pageY - canvas.offsetTop;
    }
  }
  
  function myDown(e){
    if (e.pageX < x + 15 + canvas.offsetLeft && e.pageX > x - 15 +
    canvas.offsetLeft && e.pageY < y + 15 + canvas.offsetTop &&
    e.pageY > y -15 + canvas.offsetTop){
      x = e.pageX - canvas.offsetLeft;
      y = e.pageY - canvas.offsetTop;
      dragOk = true;
      canvas.onmousemove = myMove;
    }
  }
  
  function myUp(){
    dragOk = false;
    canvas.onmousemove = null;
  }
  
  init();
  canvas.onmousedown = myDown;
  canvas.onmouseup = myUp;
  })

</script>


<h2 class="title">드래그 앤 드랍</h2>
<span class="date">2021-03-11</span>
<p class="description">
</p>


<canvas id="canvas" width="1000px" height="500px"></canvas>



<style>
  #canvas {
    margin-top: 50px;
  }

</style>