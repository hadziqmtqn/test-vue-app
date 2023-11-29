<template>
    <div>
        <h1>Data Pengguna</h1>
        <ul>
            <li v-for="user in users" :key="user.id">
                {{ user.name }} - {{ user.email }}
            </li>
        </ul>
    </div>
</template>
  
<script>
    import axios from 'axios';
    
    export default {
        data() {
            return {
                users: [],
            };
        },
        mounted() {
            this.getUsers();
        },
        methods: {
            getUsers() {
                // Menggunakan axios untuk mendapatkan data dari API
                axios.get('http://localhost:8000/api/v1/users')
                .then(response => {
                    // Mengupdate data users dengan hasil respons dari API
                    this.users = response.data.data;
                })
                .catch(error => {
                    console.error('Error fetching data:', error);
                });
            },
        },
    };
</script>
  