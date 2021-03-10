<script>

  import { onMount } from 'svelte';
  
  
  onMount(()=> {
    let mycanvas = document.getElementById("mycanvas");
    let ctx = mycanvas.getContext('2d');
    ctx.font = '48px serif';
    ctx.fillText('Hello world', 10, 50);
    
    let canvas = document.getElementById('canvas');
    let ctx2 = canvas.getContext('2d');
    ctx2.font = '48px serif';
    ctx2.strokeText('Hello world', 10, 50);

    let canvas3 = document.getElementById('canvas3');
    let ctx3 = canvas3.getContext('2d');
    ctx3.font = '100px serif';
    ctx3.textBaseline = 'middle';
    ctx3.strokeText('Hello world', 0, 100);
  })
  </script>
  
  <h2 class="title">텍스트 그리기</h2>
  <span class="date">2021-03-10</span>
  <p class="description">
    <strong>fillText(text, x, y [, maxWidth])</strong> <br/>
    주어진 (x, y) 위치에 주어진 텍스트를 채웁니다. 최대 폭(width)은 옵션 값 입니다.<br/>

  <strong>strokeText(text, x, y [, maxWidth])</strong> <br/>
  주어진 (x, y) 위치에 주어진 텍스트를 칠(stroke)합니다. 최대 폭(width)은 옵션 값 입니다. <br/>

  </p>
  
  <canvas id="mycanvas"></canvas>
  <canvas id="canvas"></canvas>
  
  <h2 class="title">텍스트 스타일 적용하기</h2>
  <p class="description">
    <strong>font = value</strong>  <br/>
    텍스트를 그릴 때 사용되는 현재 텍스트 스타일. 이 문자열은 CSS font 프로퍼티와 동일한구문을 사용합니다. 기본값으로 sans-serif의 10px가 설정되어 있습니다. <br/>

    <strong>textAlign = value</strong>  <br/>
    텍스트 정렬 설정. 사용가능한 값: start, end, left, right, center. 기본 값은 start 입니다. <br/>
    
    <strong>textBaseline = value</strong> <br/>
    베이스라인 정렬 설정. 사용가능한 값: top, hanging, middle, alphabetic, ideographic, bottom. 기본 값은 alphabetic 입니다 <br/>
    
    <strong>direction = value</strong> <br/>
    글자 방향. 사용가능한 값: ltr, rtl, inherit. 기본 값은 inherit 입니다. <br/>
  </p>

  <canvas id="canvas3" width="600px" height="auto"></canvas>

  <style lang="scss">
      @import url("./canvasText.css");

      #canvas3 {
        border: 1px solid red;
      }
  </style>
  