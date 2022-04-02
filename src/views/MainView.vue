<script setup>
    import Sidebar from "@/components/Sidebar.vue";
    import Uporabniki from "@/components/Uporabniki.vue";
</script>

<template>
  <div class="main">
    <Sidebar/>
    <Uporabniki/>
  </div>
</template>

<style>
/* @media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
} */
.main {
  display: inline-flex;
  position: relative;
}
</style>
