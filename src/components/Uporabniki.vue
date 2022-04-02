<script setup>
 import AddNewUserForm from "@/components/AddNewUserForm.vue";
 import ListOfUsers from "@/components/ListOfUsers.vue";
</script>

<template>
  <div class="main-wrapper">
      <h1> Uporabniki </h1>
      <div class="userName-wrapper">
        <p>Gašper Babnik</p> 
      </div>
      <AddNewUserForm />
      <ListOfUsers />
  </div>
</template>
<style scoped>

.main-wrapper{
  position: relative;
  float: left;
  padding: 1rem;
  width: calc(100vw - var(--sidebar-width));
  background: #F7F8FC;
}

.userName-wrapper {
  display: inline-flex;
  float: right;
}
</style>
