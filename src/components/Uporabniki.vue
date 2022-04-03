<script setup>
 import AddNewUserForm from "@/components/AddNewUserForm.vue";
 import ListOfUsers from "@/components/ListOfUsers.vue";
//  const baseURL = 'https://my-json-server.typicode.com/ForeachLabs/test-task/users'; // 'http://localhost:3000/users'; //
</script>

<template>
<div class="main-wrapper">
  <header>
      <h1> Uporabniki </h1>
      <div class="userName-wrapper">
        <p class="name-name">Gašper Babnik</p>
        <div class="name-logo">GB</div> 
      </div>
  </header>
  <AddNewUserForm />
  <ListOfUsers />
  </div>
</template>
<style scoped>

header {
 display: inline;
 vertical-align: middle;
}

.main-wrapper{
  padding: 1rem;
  width: calc(100vw - var(--sidebar-width));
  background: #F7F8FC;
}

.userName-wrapper {
  display: inline;
  float: right;
  line-height: 40px;

}
.name-name {
  float: left;
  text-align: center;
  font-family: 'Mulish';
  font-style: normal;
  font-weight: 600;
  vertical-align: middle;
  margin: 5px;
  color: #252733;
}
.name-logo {
  float: right;
  width: 42px;
  height: 42px;
  margin: 5px;
  font-weight: 700;
  font-size: 18px;
  color: #9FA2B4;
  border: 1.5px solid #DFE0EB;
  border-radius: 100%;
  text-align: center;
  vertical-align: middle; 
}
</style>
