
<script>
  import { onMount } from 'svelte';


  onMount(()=> {

    let ctx = document.getElementById('canvas').getContext('2d');
    let img = new Image();

    function draw() {
      img.onload = function() {
        ctx.drawImage(img, 0, 0);
        ctx.beginPath();
        ctx.moveTo(30, 96);
        ctx.lineTo(70, 66);
        ctx.lineTo(103, 76);
        ctx.lineTo(170, 10);
        ctx.stroke();
      };
      img.src = 'https://mdn.mozillademos.org/files/5395/backdrop.png';
    }
    draw();
  })

</script>


<h2 class="title">기본 선 그래프</h2>
<span class="date">2021-03-12</span>
<p class="description">
  drawImage()에 선을 이용하여 그래프 그리기
</p>


<canvas id="canvas" width="1000px" height="500px"></canvas>



<style>
  #canvas {
    margin-top: 50px;
  }

</style>