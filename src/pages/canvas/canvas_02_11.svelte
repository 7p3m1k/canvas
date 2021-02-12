  <script>
    import { onMount } from 'svelte';
    
    onMount(()=> {
      let myCanvas = document.getElementById("myCanvas");
      let ctx = myCanvas.getContext('2d');
  
        // 백그라운드 그리기
      ctx.fillStyle = '#FD0';
      ctx.fillRect(0, 0, 75, 75);
      ctx.fillStyle = '#6C0';
      ctx.fillRect(75, 0, 75, 75);
      ctx.fillStyle = '#09F';
      ctx.fillRect(0, 75, 75, 75);
      ctx.fillStyle = '#F30';
      ctx.fillRect(75, 75, 75, 75);
      ctx.fillStyle = '#FFF';
  
      // 투명도값 설정 
      ctx.globalAlpha = 0.2;
  
      // 반투명한 원 그리기
      for (let i = 0; i < 7; i++) {
        ctx.beginPath();
        ctx.arc(75, 75, 10 + 10 * i, 0, Math.PI * 2, true);
        ctx.fill();
      }
    })
    </script>
    
    <h2 class="title">투명도</h2>
    <span class="date">2021-02-11</span>
    <p class="description">
      globalAlpha = transparencyValue(투명도값)
      캔버스에 그려지는 모든 향후 모양에 지정된 투명도 값을 적용한다. (이건 0.2를 준상태)<br/> 
      값은 0.0 (완전 투명)에서 1.0 (완전 불투명) 사이 여야합니다. 디폴트는 1.0 (완전 불투명)임.<br/> 
      <br/> <br/> 
      4색의 네모 백그라운드를 그린다음에 반투명한 원을 그려보았다.
    </p>
    
    <canvas id="myCanvas" width="1000" height="600"></canvas>
    
    
    <style>
        @import url("./canvasText.css");
    </style>
    