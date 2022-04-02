<script setup>

</script>

<template>
  <div class="wrapper">
    <div class="intermatic-logo">
      <img src="@/assets/image4.png" />
    </div>
    <ul class="list-wrapper">
        <li class="title">
          <img src="@/assets/pie-chart-logo.png" />
          <div>Uporabniki</div>
        </li>
    </ul>
  </div>
</template>

<style scoped>
  .wrapper {
    width: var(--sidebar-width); 
    height: 100vh;
    left: 0px;
    top: 0px;
    background: #1A303D;
  }
  .intermatic-logo {
    height: 32px;
    left: 32px;
    top: 37px;
  }
  .intermatic-logo img {
    width: 180px;
    height: 32px;
    left: 2px;
    top: 3px;
  }
  .list-wrapper{
    height: 20px;
    left: 20px;
    right: 20px;
    top: calc(12% - 20px/2);
  }
  .title {
    display: inline-flex;
    font-family: 'Mulish';
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    line-height: 20px;
    letter-spacing: 0.2px;
    color: #A4A6B3;
  }
   .title div {
    left: 2rem;
    right: 0;
    height: 1rem;
    width: 1rem;

   }
   .title img {
    left: 0%;
    right: 0%;
    height: 1rem;
    width: 1rem;
   }
</style>
