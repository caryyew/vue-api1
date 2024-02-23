<template>
    <div>
        <table class="table">
      <thead>
        <tr>
          <th scope="col">Id</th>
          <th scope="col">Name</th>
          <th scope="col">Email</th>
          <th scope="col">Website</th>
          <th scope="col">Company</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="user in users" :key="user.id">
          <th scope="row">{{ user.id }}</th>
          <td>{{user.name}}</td>
          <td>{{user.male}}</td>
          <td>{{ user.website }}</td>
          <td>{{ user.company.name }}</td>
        </tr>
      </tbody>
    </table>
    </div>
    </template>
    
    <script>
    import axios from 'axios'
    export default {
        data() {
            return {
                users: null,
            };
        },
        created: function() {
            axios.get("https://jsonplaceholder.typicode.com/users").then(res => {
                this.users = res.data;
                console.log(this.users);
            })
        }
    }
    </script>