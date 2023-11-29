<!-- UserView.vue -->
<template>
    <div>
        <h1>My Main View</h1>
        <router-link to="/users">Go to Users</router-link>
        <!-- Tambahkan tag UsersList di sini -->
        <UsersList />
        <router-view></router-view>
    </div>
  </template>
  
  <script>
  import UsersList from '@/components/UsersList.vue';
  
  export default {
    components: {
        UsersList,
    },
  };
  </script>
  
  <style>
  /* Styling untuk komponen ini */
  </style>
  