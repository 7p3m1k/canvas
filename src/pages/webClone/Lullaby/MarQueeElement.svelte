<script>

</script>


  <div class="marquee">
    <p>Free Shipping & Free Returns</p>
    <p>Free Shipping & Free Returns</p>
    <p>Free Shipping & Free Returns</p>
    <p>Free Shipping & Free Returns</p>
    <p>Free Shipping & Free Returns</p>
  </div>

<style>

.marquee {
  width:auto;
  height: 58px;
  overflow:hidden;
  background-color:black;
  color: white;
  display: flex;
  font-size: 25px;
  align-items: center;
}

.marquee p {
  margin:0;
  padding-left:50px;
  display:inline-block;
  white-space:nowrap;
    animation-name:marquee;
    animation-timing-function:linear;
    animation-duration:10s;
    animation-iteration-count:infinite;
}

@keyframes marquee {
  from   { transform: translate(0%);}
  99%,to { transform: translate(-100%);}
}
</style>