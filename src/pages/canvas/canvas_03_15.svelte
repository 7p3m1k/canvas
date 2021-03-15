
<script>
  import { onMount } from 'svelte';


  onMount(()=> {

    let ctx = document.getElementById('canvas').getContext('2d');
    let img = new Image();

    function draw() {
      img.onload = function() {
        for (let i = 0; i < 4; i++) {
          for (let j = 0; j < 3; j++) {
            ctx.drawImage(img, j * 150, i * 138, 150, 138);
          }
        }
      };
    img.src = 'https://mdn.mozillademos.org/files/5397/rhino.jpg';
    }
    draw();
  });
</script>


<h2 class="title">이미지를 타일처럼 배치</h2>
<span class="date">2021-03-15</span>
<p class="description">
  첫 번째 for루프는 행을 반복합니다. 두 번째 for루프는 열을 반복합니다. 이미지는 원래 크기 인 150x138 픽셀의 1/3로 조정됩니다.
</p>


<canvas id="canvas" width="1000px" height="500px"></canvas>



<style>
  #canvas {
    margin-top: 50px;
  }

</style>