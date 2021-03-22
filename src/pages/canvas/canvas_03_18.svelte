
<script>
  import { onMount } from 'svelte';


  onMount(()=> {
    let ctx = document.getElementById('canvas').getContext('2d');
      // 좌측 사각형, canvas 원점에서 회전하기
    ctx.save();
    // 파란 사각형
    ctx.fillStyle = 'blue';
    ctx.fillRect(30, 30, 100, 100);
    ctx.rotate((Math.PI / 180) * 25);
    // 붉은색 사각형 그리기
    ctx.fillStyle = 'red';
    ctx.fillRect(30, 30, 100, 100);
    ctx.restore();

    // 우측 사각형, 사각형 중심에서 회전하기
    // 파란 사각형 그리기
    ctx.fillStyle = 'blue';
    ctx.fillRect(150, 30, 100, 100);

    ctx.translate(200, 80); // 사각형 중심으로 이동하기
                            // x = x + 0.5 * width
                            // y = y + 0.5 * height
    ctx.rotate((Math.PI / 180) * 25); // 회전
    ctx.translate(-200, -80); // 예전 위치로 이동하기

    // 붉은색 사각형 그리기
    ctx.fillStyle = 'red';
    ctx.fillRect(150, 30, 100, 100);
  });
</script>


<h2 class="title">회전(rotating)</h2>
<span class="date">2021-03-18</span>
<p class="description">
  <br/>
  rotate() : canvas를 현재의 원점 둘레로 회전하는 데 사용. <br/>
  회전의 중심점은 언제나 canvas 원점. 중심점을 바꾸려면 translate() 메소드를 써서 canvas를 이동해야 됨.<br/><br/>
  <strong>주의: 각도의 단위는 도(degree)가 아닌 라디안(radian). 변환하려면 radians = (Math.PI/180)*degrees.를 사용 해야한다.</strong>
</p>


<canvas id="canvas" width="1000px" height="500px"></canvas>



<style>
  #canvas {
    margin-top: 50px;
    margin-left: 50px;
  }

</style>