<script>
  import { onMount } from 'svelte';
  
  onMount(()=> {
    let myCanvas = document.getElementById("myCanvas");
    let ctx = myCanvas.getContext('2d');

    for (let i = 0; i < 10; i++) {
      ctx.lineWidth = 1 + i;
      ctx.beginPath();
      ctx.moveTo(5 + i * 14, 5);
      ctx.lineTo(5 + i * 14, 140);
      ctx.stroke();
    }
  })
  </script>
  
  <h2 class="title">선 스타일</h2>
  <span class="date">2021-02-12</span>
  <p class="description">
    <strong>lineWidth = value</strong><br/>
    앞으로 그려지는 선의 너비를 설정합니다.<br/><br/>

    <strong>lineCap = type</strong><br/>
    선 끝의 모양을 설정합니다.<br/><br/>

    <strong>lineJoin = type</strong><br/>
    선이 만나는 "코너"의 모양을 설정합니다.<br/><br/>

    <strong>miterLimit = value</strong><br/>
    두 선이 날카로운 각도로 결합 할 때 마이 터에 제한을 설정하여 접합부의 두께를 제어 할 수 있습니다.<br/><br/>

    <strong>getLineDash()</strong><br/>
    음수가 아닌 짝수를 포함하는 현재 선 대시 패턴 배열을 반환합니다.<br/><br/>

    <strong>setLineDash(segments)</strong><br/>
    현재 선 대시 패턴을 설정합니다.<br/><br/>

    <strong>lineDashOffset = value</strong><br/>
    선에서 대시 배열을 시작할 위치를 지정합니다.<br/>
  </p>
  <h1>lineWidth 예</h1>
  <p class="description">선의 굵기가 점점 굵어지는 10 개의 직선.<br/> 
    맨 왼쪽의 선은 너비는 1.0이다.<br/> 가장 왼쪽 및 다른 모든 홀수 정수 너비의 두께 선은 <strong>경로의 위치 때문에</strong> 선명하게 나타나지 않습니다.</p>
  <canvas id="myCanvas" width="1000" height="600"></canvas>
  
  
  <style>
      @import url("./canvasText.css");
  </style>
  