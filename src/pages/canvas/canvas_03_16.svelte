
<script>
  import { onMount } from 'svelte';


  onMount(()=> {
    let ctx = document.getElementById('canvas').getContext('2d');
    ctx.fillStyle = 'yellow';
      ctx.fillRect(0, 0, 150, 150);   // 기본 설정으로 사각형을 그리기
      ctx.save();                  // 기본 상태를 저장하기

      ctx.fillStyle = 'blue';      // 설정 변경하기
      ctx.fillRect(15, 15, 120, 120); // 새로운 설정으로 사각형 그리기

      ctx.save();                  // 현재 상태 저장하기
      ctx.fillStyle = 'red';      // 설정 변경하기
      ctx.globalAlpha = 0.5;
      ctx.fillRect(30, 30, 90, 90);   // 새로운 설정으로 사각형 그리기

      ctx.restore();               // 이전 상태 복원하기
      ctx.fillRect(45, 45, 60, 60);   // 복원된 설정으로 사각형 그리기

      ctx.restore();               // 초기 상태를 복원하기
      ctx.fillRect(60, 60, 30, 30);   // 복원된 설정으로 사각형 그리기
  });
</script>


<h2 class="title">save와 restore canvas 상태(state) 예제</h2>
<span class="date">2021-03-16</span>
<p class="description">
  <br/>
  save() : canvas의 모든 상태를 저장.<br/>
  restore() : 가장 최근에 저장된 canvas 상태를 복원.
</p>


<canvas id="canvas" width="1000px" height="500px"></canvas>



<style>
  #canvas {
    margin-top: 50px;
  }

</style>