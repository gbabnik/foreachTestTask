<script setup>
 
</script>

<template>
  <div class="userList-wrapper">
    <h2>Seznam uporabnikov</h2>
    <table>
        <tr>
            <th>Ime</th>
            <th>Priimek</th>
            <th>Uporabniško ime</th>
        </tr>
        <tr>
            <td>Janez</td>
            <td>Lajovic</td>
            <td>janez.lajovic</td>
        </tr>
    </table> 
  </div>
</template>

<style scoped>
.userList-wrapper {
  max-width: calc(100vw - var(--sidebar-width) - 2rem);
  min-height: 400px;
  background: #FFFFFF;
  border: 1px solid #DFE0EB;
  border-radius: 8px;
  margin: 10px 0px;
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
