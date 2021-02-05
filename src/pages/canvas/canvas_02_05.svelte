<script>
  import { onMount } from 'svelte';
  
  onMount(()=> {
    let canvas = document.getElementById("canvas");
    let ctx = canvas.getContext('2d');

    let rectangle = new Path2D();
    rectangle.rect(10, 10, 50, 50);

    let circle = new Path2D();
    circle.arc(100, 35, 25, 0, 2 * Math.PI);

    ctx.stroke(rectangle);
    ctx.fill(circle);
    ctx.fill(hi);
    })

  </script>
  
  <h2 class="title">Path2D 객체</h2>
  <span class="date">2021-02-05</span>
  <p class="description">
    Path2D() <br/>
    Path2D()생성자 새로이 초기화 반환 Path2D선택적 인수로서 다른 경로 (복사본을 생성)하여, 개체, 또는 선택적으로 구성된 문자열 SVG 경로 데이터.
  </p>
  
  <canvas id="canvas" width="1000" height="600"></canvas>
  
  
  <style>
      @import url("./canvasText.css");
  </style>
  
  