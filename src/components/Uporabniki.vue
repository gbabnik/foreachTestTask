<script setup>
</script>
<script>
import axios from 'axios';
const baseURL = 'https://my-json-server.typicode.com/ForeachLabs/test-task/users'; //'http://localhost:3000/users'; //
  export default {
    data() {
      return {
        userData: [],
        newUserData: {
                      name: '',
                      surname: '',
                      username: '',
                      password: '' 
                      } 
      };
    },
    async created() {
        try {
          const response = await axios.get(baseURL);
          this.userData = response.data;
          console.log(response);
        } catch(e) {
          console.error(e);
        }
    },
    methods: {
      async postUser(){
        await axios.post(baseURL, this.newUserData)
          .then((response)=>{
            console.log(response.data.id);
            this.userData = [...this.userData, response.data];
            this.newUserData = '';
          }).catch(error => {
            console.log(error);
          })
      }
    }
  };
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
  <!-- <AddNewUserForm /> -->
   <div class="userForm-wrapper">
    <h2>Nov uporabnik</h2>
    <form @submit.prevent="postUser" method="post">
      <input type="text" placeholder="Ime" required v-model="newUserData.name">
      <input type="text" placeholder="Priimek" required v-model="newUserData.surname">
      <input type="text" placeholder="Uporabniško ime" required v-model="newUserData.username">
      <input type="password" placeholder="Geslo" required v-model="newUserData.password">
      <button type="submit">Dodaj uporabnika</button>  
    </form>
  </div>
  <!-- <ListOfUsers /> -->
  <div class="userList-wrapper">
    <h2>Seznam uporabnikov</h2>
    <table>
        <tr>
            <th>Id</th>
            <th>Ime</th>
            <th>Priimek</th>
            <th>Uporabniško ime</th>
            
        </tr>
        <tr v-for="user of userData" :key="user.id">
            <td>{{user.id}}</td>
            <td>{{user.name}}</td>
            <td>{{user.surname}}</td>
            <td>{{user.username}}</td>         
        </tr>
        </table>
    </div>
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

.userList-wrapper {
  max-width: calc(100vw - var(--sidebar-width) - 2rem);
  min-height: 400px;
  background: #FFFFFF;
  border: 1px solid #DFE0EB;
  border-radius: 8px;
  margin: 10px 0px;
}

.userForm-wrapper {
  max-width: calc(100vw - var(--sidebar-width) - 2rem);
  min-height: 400px;
  background: #FFFFFF;
  border: 1px solid #DFE0EB;
  border-radius: 8px;
  margin: 10px 0px;
}

.input_fields_wrapper {
  position: relative;
  display: flex;
  width: 90%;
  margin: 0;
}

table {
   font-size: 14px; 
   width: 100%; 
}

tr {
    height: 92px;  
}

th {
    vertical-align: bottom;
    text-align: left;
    font-weight: 700;
    color: #9FA2B4;
    padding: 20px;
    border: 0;
    border-bottom: 1.5px solid #DFE0EB;
}
td {
    text-align: left;
    font-weight: 600;
    color: #252733;
    border: 0;
    border-bottom: 1px solid #DFE0EB;
    padding: 20px;
}
</style>
