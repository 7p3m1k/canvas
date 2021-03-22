
<script>
  import { onMount } from 'svelte';


  onMount(()=> {
    let ctx = document.getElementById('canvas').getContext('2d');
    let ctx2 = document.getElementById('canvas2').getContext('2d');
    let ctx3 = document.getElementById('canvas3').getContext('2d');
    let ctx4= document.getElementById('canvas4').getContext('2d');
    // 간단하지만 확대·축소 비율을 적용한 사각형 그리기
    ctx.save();
    ctx.scale(10, 3);
    ctx.fillRect(1, 10, 10, 10);
    ctx.restore();

    // 수평으로 대칭하기
    ctx.font = '48px serif';
    ctx.fillText('안녕', 0, 120);

    ctx2.save();
    ctx2.scale(10, 3);
    ctx2.fillRect(1, 10, 10, 10);
    ctx2.restore();

    // 수평으로 대칭하기
    ctx2.scale(-1, -1);
    ctx2.font = '48px serif';
    ctx2.fillText('안녕', -135, -120);

    ctx3.save();
    ctx3.scale(10, 4);
    ctx3.fillRect(1, 10, 20, 10);
    ctx3.restore();

    ctx3.scale(-1, 1);
    ctx3.font = '48px serif';
    ctx3.fillText('안녕', -135, 120);

    ctx4.strokeRect(10,10,30,30);
    ctx4.scale(3,3);
    ctx4.strokeRect(10,10,30,30);
  });
</script>


<h2 class="title">확대·축소(scaling)</h2>
<span class="date">2021-03-19</span>
<p class="description">
  <br/>
  
</p>


<canvas id="canvas" width="300px" height="300px"></canvas>
<canvas id="canvas2" width="300px" height="300px"></canvas>
<canvas id="canvas3" width="300px" height="300px"></canvas>
<canvas id="canvas4" width="300px" height="300px"></canvas>



<style>
  #canvas {
    margin-top: 50px;
  }

</style>