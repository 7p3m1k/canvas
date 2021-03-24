
<script>
  import { onMount } from 'svelte';


  onMount(()=> {
    let ctx = document.getElementById('canvas').getContext('2d');

    // 그레이디언트를 생성한다
    let lingrad = ctx.createLinearGradient(0, 0, 0, 150);
    lingrad.addColorStop(0, '#00ABEB');
    lingrad.addColorStop(0.5, '#fff');
    lingrad.addColorStop(0.5, '#26C000');
    lingrad.addColorStop(1, '#fff');

    let lingrad2 = ctx.createLinearGradient(0, 50, 0, 95);
    lingrad2.addColorStop(0.5, '#000');
    lingrad2.addColorStop(1, 'rgba(0, 0, 0, 0)');

    // 외곽선과 채움 스타일에 그레이디언트를 적용한다
    ctx.fillStyle = lingrad;
    ctx.strokeStyle = lingrad2;

    // 도형을 그린다
    ctx.fillRect(10, 10, 130, 130);
    ctx.strokeRect(50, 50, 50, 50);
  });
</script>


<h2 class="title">createLinearGradient</h2>
<span class="date">2021-03-22</span>
<p class="description">
  <br/>
  <strong>strokeStyle</strong>과 <strong>fillStyle</strong> 속성 모두 <strong>canvasGradient</strong> 오브젝트를 속성 값으로 가질 수 있다.
</p>

<div>
  <canvas id="canvas" width="1000px" height="1000px"></canvas>
</div>




<style>
  #canvas {
    margin-top: 50px;
    margin-left: 50px;
  }

  div {
    background-color: black;
  }

</style>