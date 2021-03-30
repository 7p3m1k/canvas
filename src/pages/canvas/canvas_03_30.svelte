<script>
  import { onMount } from 'svelte';
  
  onMount(()=> {
    let Canvas = document.getElementById("Canvas");
    let ctx = Canvas.getContext('2d');

		var gradient = ctx.createLinearGradient(0, 0, 200, 0);
		gradient.addColorStop(0, "blue");
		gradient.addColorStop(1, "green");

		ctx.fillStyle = gradient;
		ctx.font = '100px serif';
		ctx.fillText("Park Min Kyu", 15, 120);
  })

  </script>
  
  <h2 class="title">선형 그래디언트 그리기</h2>
  <span class="date">2021-03-30</span>
  <p class="description">

    </p>
  <div>
    <canvas id="Canvas" width="1000" height="300"></canvas>
  </div>
  <style>
      @import url("./canvasText.css");


  </style>
