<script setup>

</script>

<template>
  <div class="wrapper">
    <div class="intermatic-logo">
      <img src="@/assets/image4.png" />
    </div>
    <ul>
        <li>
          <div>Uporabniki</div>
        </li>
    </ul>
  </div>
</template>

<style scoped>
  .wrapper {
    width: var(--sidebar-width); 
    min-height: 100vh;
    background: #1A303D;
  }
  .intermatic-logo {
    height: 32px;
    left: 32px;
    top: 37px;
  }
  ul{
    height: 20px;
    left: 20px;
    right: 20px;
    top: calc(12% - 20px/2);
    /* list-style: url('@/assets/pie-chart-logo.png'); */
  }
  li{
    font-family: 'Mulish';
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    line-height: 20px;
    letter-spacing: 0.2px;
    padding: 1rem 2rem;
    color: #A4A6B3;
    list-style: url('@/assets/pie-chart-16.png');
  }
</style>
