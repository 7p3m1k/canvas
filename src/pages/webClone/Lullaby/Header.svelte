<script>

  let current ;

</script>


<div class="header">
  <div class="header-wrapper">
    <div class="logo">Maden</div>
    <ul>
      <li on:mouseover={() => current = 'Lookbook'}>Lookbook</li>
      <li on:mouseover={() => current = 'Shop'}>Shop</li>
      <li on:mouseover={() => current = ''}>Notice</li>
      <li on:mouseover={() => current = ''}>About us</li>
    </ul>
    <div>
      <span>Cart</span>
      <span>Login</span>
    </div>
  </div>
</div>

{#if current === 'Lookbook'}
  <ul class="lookbook-menu" on:mouseleave={() => current = ''}> 
    <li>2020</li>
    <li>2019</li>
    <li>2018</li>
  </ul>
{/if}

{#if current === 'Shop'}
<ul>
  <li>top</li>
  <li>bottom</li>
  <li>shoes</li>
  <li>bag</li>
</ul>
{/if}


<style lang="scss">
  .header {
  position: sticky;
    top: 0;
    left: 0;
    right: 0;
    z-index: 99;
    background-color: rgba(255,255,255,0.9);
    border-bottom: 1px solid black;

    .header-wrapper {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 0 15px;
      height: 90px;

      .logo {
        font-family: Gilroy;
        font-size: 36px;
        font-weight: bold;
        cursor: pointer;
      }

      li {
        float: left;
        padding: 0 18px;
        cursor: pointer;
      }

      li:hover {
        color: gray;
      }

      span {
        padding: 0 6px;
        cursor: pointer;
      }
    }
  }
  .lookbook-menu {
    margin-left: 550px;
    width: 158px;

    li {
      border: 1px solid black;
      border-top: none;
      cursor: pointer;
      padding: 10px 20px;
    }

    li:first-child {
        border-top: none;
      }
  }
</style>