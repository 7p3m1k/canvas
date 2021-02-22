<script>
  import { onMount } from 'svelte';


  onMount(()=> {
    let myCanvas = document.getElementById("myCanvas");
    let ctx = myCanvas.getContext('2d');

    const radian = Math.PI / 180 ;

    const radius = 150;
    const rotateDegree = 32;

    const rectWidth  = radius;
    const rectHeight = radius / 6;
    const rectMargin = radius / 12;

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

    // //보조선
    // ctx.beginPath();
    // ctx.arc(
    //   radius * 3,
    //   radius * 2,
    //   radius + radius * ( 1 / 2 ),
    //   0 * radian,
    //   360 * radian,
    //   true
    // )
    // ctx.stroke();

    //건 부분
    ctx.resetTransform();
    ctx.translate(300,110);
    ctx.rotate(90);
    ctx.fillStyle='black';
    ctx.beginPath();
    ctx.fillRect(0, 0, radius, radius / 6);

    ctx.beginPath();
    ctx.fillRect(0, rectHeight + rectMargin , rectWidth, rectHeight);

    ctx.beginPath();
    ctx.fillRect(0, rectHeight * 2 + rectMargin * 2 , rectWidth, rectHeight);

    //리 부분
    ctx.resetTransform();
    ctx.translate(220,345);
    ctx.rotate((30 + rotateDegree) * radian);
    ctx.fillStyle='black';
    ctx.beginPath();
    ctx.fillRect(0, 0, radius, radius / 6);

    ctx.beginPath();
    ctx.fillRect(0, rectHeight + rectMargin , rectWidth, rectHeight);

    ctx.beginPath();
    ctx.fillRect(0, rectHeight * 2 + rectMargin * 2 , rectWidth, rectHeight);

    //흰색 부분
    ctx.resetTransform();
    ctx.translate(253,405);
    ctx.rotate((30 + rotateDegree) * radian);
    ctx.fillStyle='white';
    ctx.beginPath();
    ctx.fillRect(0, rectHeight + rectMargin, rectMargin, rectHeight + 10);

    //감 부분
    ctx.resetTransform();
    ctx.translate(680,55);
    ctx.rotate((25 + rotateDegree) * radian);
    ctx.fillStyle = 'black';
    ctx.beginPath();
    ctx.fillRect(0, 0, rectWidth, rectHeight);

    ctx.beginPath();
    ctx.fillRect(0, rectHeight + rectMargin , rectWidth, rectHeight);

    ctx.beginPath();
    ctx.fillRect(0, rectHeight * 2 + rectMargin * 2 , rectWidth, rectHeight);

    //흰색 부분
    ctx.resetTransform();
    ctx.translate(720,110);
    ctx.rotate((25 + rotateDegree) * radian);
    ctx.fillStyle = 'white';
    ctx.beginPath();
    ctx.fillRect(0, rectHeight * 2 + rectMargin * 2, rectMargin, rectHeight + 10);

    ctx.resetTransform();
    ctx.translate(720,110);
    ctx.rotate((25 + rotateDegree) * radian);
    ctx.fillStyle = 'white';
    ctx.beginPath();
    ctx.fillRect(0, 0, rectMargin, rectHeight + 10);

    //곤 부분
    ctx.resetTransform();
    ctx.translate(610,470);
    ctx.rotate((-90 + rotateDegree) * radian);
    ctx.fillStyle = 'black';
    ctx.beginPath();
    ctx.fillRect(0, 0, rectWidth, rectHeight);

    ctx.beginPath();
    ctx.fillRect(0, rectHeight + rectMargin , rectWidth, rectHeight);

    ctx.beginPath();
    ctx.fillRect(0, rectHeight * 2 + rectMargin * 2 , rectWidth, rectHeight);

    //흰색 부분
    ctx.resetTransform();
    ctx.translate(580,370);
    ctx.rotate((-90 + rotateDegree) * radian);
    ctx.fillStyle = 'white';
    ctx.beginPath();
    ctx.fillRect(0, rectHeight * 2 + rectMargin * 2, rectMargin, rectHeight + 100);
  })
</script>


<h2 class="title">태극기</h2>
<span class="date">2021-02-22</span>
<p class="description">
</p>


<canvas id="myCanvas" width="900" height="600"></canvas>


<style>
  @import url("./canvasText.css");

  canvas {
    background-color: white;
    border: 1px solid black;
  }
</style>