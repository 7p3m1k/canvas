<script>

  import { onMount } from 'svelte';
  
  onMount(()=> {
    let mycanvas = document.getElementById("mycanvas");
    let ctx = mycanvas.getContext('2d');

    // const imgElem = document.createElement('img');    // 둘다 같은 것
    const imgElem = new Image();
    imgElem.src = 'https://source.unsplash.com/random';
    imgElem.addEventListener('load',()=> {
      ctx.drawImage(imgElem, 50, 50);
      ctx.drawImage(imgElem, 50, 50, 70, 120);
    })


  })
  </script>
  
  <h2 class="title">이미지 넣기 (drawImage)</h2>
  <span class="date">2021-03-02</span>
  <p class="description">
    drawImage를 이용하여 캔버스에 이미지를 넣어줌
  </p>
  
  <canvas id="mycanvas" width="1000" height="1000"></canvas>
  
  
  <style>
      @import url("./canvasText.css");
  </style>
  