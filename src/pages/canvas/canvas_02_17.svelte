<script>
import { onMount } from 'svelte';



  onMount(()=> {
    let myCanvas = document.getElementById("myCanvas");
    let ctx = myCanvas.getContext('2d');

    let myCanvas2 = document.getElementById("myCanvas2");
    let ctx2 = myCanvas2.getContext('2d');

    ctx.fillRect(0, 0, 100, 100);
    ctx2.fillRect(0, 0, 100, 100);
    ctx.fill();
    ctx2.fill();
  })


</script>

<h2 class="title">캔버스 사이즈 설정</h2>
<span class="date">2021-02-17</span>
<p class="description">
  width,height 값 설정 안하면 기본값이 300,150<br/>
  2개의 canvas에 width , height를 직접 입력해줬다. <strong>왼쪽은 (500,300)</strong>  <strong>오른쪽은 (1000,600)</strong> <br/>
  그리고 css에 width 500, height 300을 넣어줬다. 화면을 보면 2개의 크기가 같아졌다 그래도 오른쪽꺼는 여전히 1000,600 크기로 인식을한다.<br/>
  이 두개의 차이는 100,100짜리 정사각형을 그릴때 왼쪽은 500에서 100 즉 5분의1 만큼의 크기로 그려지는데 오른쪽은 1000에서 100 10분의1 크기로 그려지게된다.<br/>
  오른쪽 처럼 width , height를 주는 경우도 많다 왜냐면 image처럼 고해상도 디스플레이에서 고해상도 이미지를 표현하기 위해서다.<br/>
  상황에 따라서 속성을 주면 될꺼같다.
</p>
<strong>canvas는 풀스크린으로 쓰는 경우가 많은데 그럴때 고해상도로 하기 위해서는 js에 캔버스 사이즈를 윈도우 사이즈 2배로 셋팅을하고 css에 100%를 주면된다.</strong>


<div>
  <canvas id="myCanvas" width="500" height="300"></canvas>
  <canvas id="myCanvas2" width="1000" height="600"></canvas>
</div>



<style>
  @import url("./canvasText.css");

  canvas {
    background-color: red;
    width: 500px;
    height: 300px;
  }
</style>