<script>
  import { onMount } from 'svelte';


  onMount(()=> {
    let myCanvas = document.getElementById("myCanvas");
    let ctx = myCanvas.getContext('2d');

    const radian = Math.PI / 180 ;

    const radius = 150;
    const rotateDegree = 32;

    //빨간색 반원
    ctx.fillStyle = 'red';
    ctx.beginPath();
    ctx.arc(
      radius * 3,   //가로 450
      radius * 2,   //세로 300
      radius,
      // 0 * radian,  //각도를 넣을때는 라디안을 곱해줘야함  태극기는 32도정도 기울어져 있어서 rotateDegree = 32추가
      rotateDegree * radian,
      (180 + rotateDegree)* radian,
      true,
    )
    ctx.fill();

    //파란색 반원
    ctx.fillStyle = 'blue';
    ctx.beginPath();
    ctx.arc(
      radius * 3,   //가로 450
      radius * 2,   //세로 300
      radius,
      rotateDegree * radian, 
      (180 + rotateDegree)* radian,
      false,
    )
    ctx.fill();

    //빨간색 작은원
    ctx.fillStyle = 'red';
    ctx.beginPath();
    ctx.arc(
      387, //radius로 계산해서 해야하는데 모르겠다..
      259,
      radius /2 ,
      rotateDegree * radian, 
      (180 + rotateDegree)* radian,
      false,
    )
    ctx.fill();

    //파란색 작은원
    ctx.fillStyle = 'blue';
    ctx.beginPath();
    ctx.arc(
      512.5,  //radius로 계산해서 해야하는데 모르겠다..
      341.5,
      radius /2 ,
      rotateDegree * radian, 
      (180 + rotateDegree)* radian,
      true,
    )
    ctx.fill();
  })
</script>


<h2 class="title">태극마크 ver2 (색넣기)</h2>
<span class="date">2021-02-19</span>
<p class="description">
32도 기울어진 반지름을 이용하여 만들었다.
</p>


<canvas id="myCanvas" width="900" height="600"></canvas>


<style>
  @import url("./canvasText.css");

  canvas {
    background-color: #eee;
    border: 1px solid black;
  }
</style>