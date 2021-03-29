<script>
  import { onMount } from 'svelte';
  
  onMount(()=> {
    let Canvas = document.getElementById("Canvas");
    let ctx = Canvas.getContext('2d');

    // Draw guides
    ctx.strokeStyle = 'red';
    ctx.beginPath();
    ctx.moveTo(10, 10);
    ctx.lineTo(200, 10);
    ctx.lineTo(200, 200);
    ctx.lineTo(10, 200);
    ctx.lineTo(10, 10);
    ctx.stroke();

  })

  </script>
  
  <h2 class="title">선 그리기</h2>
  <span class="date">2021-03-29</span>
  <p class="description">
    ctx.strokeStyle = 'red'; <br/>
    ctx.beginPath();<br/>
    ctx.moveTo(10, 10);<br/>
    ctx.lineTo(200, 10);<br/>
    ctx.lineTo(200, 200);<br/>
    ctx.lineTo(10, 200);<br/>
    ctx.lineTo(10, 10);<br/>
    ctx.stroke();
    </p>
  <div>
    <canvas id="Canvas" width="1000" height="300"></canvas>
  </div>
  <style>
      @import url("./canvasText.css");

  </style>
