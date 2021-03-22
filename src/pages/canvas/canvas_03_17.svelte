
<script>
  import { onMount } from 'svelte';


  onMount(()=> {
    let ctx = document.getElementById('canvas').getContext('2d');
    for (let i = 0; i < 3; i++) {
      for (let j = 0; j < 3; j++) {
        ctx.save();
        ctx.fillStyle = 'rgb(' + (51 * i) + ', ' + (255 - 51 * i) + ', 255)';
        ctx.translate(10 + j * 50, 10 + i * 50);
        ctx.fillRect(0, 0, 25, 25);
        ctx.restore();
      }
    }
  });
</script>


<h2 class="title">이동(translating)</h2>
<span class="date">2021-03-17</span>
<p class="description">
  <br/>
  translate() : 그리드에서 canvas를 원점에서 다른 점으로 옮기는 데 사용. 
</p>


<canvas id="canvas" width="1000px" height="500px"></canvas>



<style>
  #canvas {
    margin-top: 50px;
  }

</style>