<script>
import axios from 'axios';
const baseURL = 'https://my-json-server.typicode.com/ForeachLabs/test-task/users'; // 'http://localhost:3000/users'; //
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
      async postData(){
          // console.warn(this.userData)
          const response = await axios.post(baseURL, this.newUserData);
              console.log(response);
              // this.userData = [...this.userData, response.data];
              // this.newUserData = null;
      }
    }
  }
</script>
<script setup>

</script>

<template>
  <div class="userForm-wrapper">
    <h2>Nov uporabnik</h2>
    <form @submit="postData" method="post">
      <input type="text" placeholder="Ime" required v-model="newUserData.name">
      <input type="text" placeholder="Priimek" required v-model="newUserData.surname">
      <input type="text" placeholder="Uporabniško ime" required v-model="newUserData.username">
      <input type="password" placeholder="Geslo" required v-model="newUserData.password">
      <button type="submit">Dodaj uporabnika</button>  
      <table>
        <tr>
            <th>Ime</th>
            <th>Priimek</th>
            <th>Uporabniško ime</th>
        </tr>
        <tr v-for="user of userData" :key="user.id">
            <td>{{user.name}}</td>
            <td>{{user.surname}}</td>
            <td>{{user.username}}</td>
            <td>{{newUserData.name}}</td>
        </tr>
        </table>
    </form>

  </div>
</template>

<style scoped>
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




/* @media (min-width: 1024px) {
  .item {
    margin-top: 0;
    padding: 0.4rem 0 1rem calc(var(--section-gap) / 2);
  }

  i {
    top: calc(50% - 25px);
    left: -26px;
    position: absolute;
    border: 1px solid var(--color-border);
    background: var(--color-background);
    border-radius: 8px;
    width: 50px;
    height: 50px;
  }

  .item:before {
    content: " ";
    border-left: 1px solid var(--color-border);
    position: absolute;
    left: 0;
    bottom: calc(50% + 25px);
    height: calc(50% - 25px);
  }

  .item:after {
    content: " ";
    border-left: 1px solid var(--color-border);
    position: absolute;
    left: 0;
    top: calc(50% + 25px);
    height: calc(50% - 25px);
  }

  .item:first-of-type:before {
    display: none;
  }

  .item:last-of-type:after {
    display: none;
  }
} */
</style>
