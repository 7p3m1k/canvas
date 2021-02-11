<script>
  import { onMount } from 'svelte';
  
  onMount(()=> {
    let myCanvas = document.getElementById("myCanvas");
    let ctx = myCanvas.getContext('2d');

        ctx.fillStyle = 'rgb(200, 0, 0)';
        ctx.fillRect(10, 10, 100, 100);

        ctx.fillStyle = 'rgba(0, 0, 200, 0.5)';
        ctx.fillRect(30, 30, 100, 100);
    })
  </script>


  <h2 class="title">두 개의 교차하는 직사각형,색 채워 넣기</h2>
  <span class="date">2021-02-04</span>
  <p class="description">
    https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Basic_usage <br/> 
    예제 따라하기 <br/><br/>
    ctx.fillStyle = 'color'; 를 이용하여 색을 채워 넣을 수 있다. 
  </p>
  
  <canvas id="myCanvas" width="1000" height="600"></canvas>
  
  
  <style>
      @import url("./canvasText.css");
  </style>
  