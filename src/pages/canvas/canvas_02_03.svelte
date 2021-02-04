<script>
import { onMount } from 'svelte';

 onMount(()=> {
    let myCanvas = document.getElementById("myCanvas");
    let ctx = myCanvas.getContext('2d');

    ctx.beginPath();
    ctx.moveTo(75, 40);
    ctx.bezierCurveTo(75, 37, 70, 25, 50, 25);
    ctx.bezierCurveTo(20, 25, 20, 62.5, 20, 62.5);
    ctx.bezierCurveTo(20, 80, 40, 102, 75, 120);
    ctx.bezierCurveTo(110, 102, 130, 80, 130, 62.5);
    ctx.bezierCurveTo(130, 62.5, 130, 25, 100, 25);
    ctx.bezierCurveTo(85, 25, 75, 37, 75, 40);
    ctx.fill();
  })

</script>

<h2 class="title">하트</h2>
<span class="date">2021-02-03</span>
<p class="description">
  bezierCurveTo() <br/>
  삼차 곡선을 이용하여 하트 만들기.
</p>
<h3>
  bezierCurveTo(cp1x, cp1y, cp2x, cp2y, x, y)
  (cp1x, cp1y) 및 (cp2x, cp2y)로 지정된 제어점을 사용하여 <br/>
  현재 펜 위치에서 x 및 y로 지정된 끝점까지 삼차 베지어 곡선을 그림.
</h3>

<canvas id="myCanvas" style="width:1000px; height:500px;">
</canvas>


<style>
    @import url("./canvasText.css");
</style>
