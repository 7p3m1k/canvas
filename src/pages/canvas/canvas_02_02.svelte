<script>

  function drawLine() {
    let myCanvas3 = document.getElementById("myCanvas3");
    let ctx = myCanvas3.getContext('2d');

    //삼각형
    ctx.beginPath();
    ctx.moveTo(25, 25);
    ctx.lineTo(105, 25);
    ctx.lineTo(25, 105);
    ctx.fill();

    ctx.beginPath();
    ctx.moveTo(125, 125);
    ctx.lineTo(125, 45);
    ctx.lineTo(45, 125);
    ctx.closePath();
    ctx.stroke();
  }


</script>

<h2 class="title">네모 그리기,스마일 그리기,선그리기</h2>
<span class="date">2021-02-02</span>
<p class="description">
  fillRect: 내부에 색상을 칠한 네모를 그린다. <br/>
  clearRect: 내부에 투명색을 칠한 네모를 그린다. <br/>
  strokeRect: 선으로만 이루어진 네모를 그린다.
</p>

<p class="description">
  beginPath: 선 그리기 시작을 알리는 함수. <br/>
  moveTo: 시작 점 위치를 이동한다. <br/>
  fill: 내부를 칠하며 그린다.<br/>
  stroke: 선으로 그린다.<br/>
  arc: 원 또는 타원을 그린다.
</p>

<p class="description">
  beginPath: 선 그리기 시작을 알리는 함수. <br/>
  moveTo: 시작 점 위치를 이동한다. <br/>
  fill: 내부를 칠하며 그린다.<br/>
  stroke: 선으로 그린다.<br/>
  lineTo: 선의 끔점을 설정한다.
</p>

<div>
  <canvas id="myCanvas" style="width:300px; height:300px; border:1px solid red"></canvas>
  <canvas id="myCanvas2" style="width:300px; height:300px; border:1px solid red"></canvas>
  <canvas id="myCanvas3" style="width:300px; height:300px; border:1px solid red"></canvas>
</div>

<button on:click={drawRect}>네모 !</button>
<button on:click={drawArc}>원 !</button>
<button on:click={drawLine}>선 !</button>


<style>
    @import url("./canvasText.css");

  div {
    display: flex;

  }
</style>