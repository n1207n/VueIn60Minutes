<template>
  <div class="users">
    <h1>Users</h1>

    <ul>
      <li v-for="user in users">{{user.name}}: {{user.email}}</li>
    </ul>

    <form v-on:submit="addUser">
      <input type="text" v-model="newUser.name" placeholder="Enter Name" />
      <br>
      <input type="text" v-model="newUser.email" placeholder="Enter Email" />
      <br>
      <input type="submit" value="Submit" />
    </form>
  </div>
</template>

<script>
export default {
  name: 'users',
  data() {
    return {
      newUser: {},
      users: [
        {
          name: 'John Doe',
          email: 'jdoe@gmail.com',
          contacted: false,
        },
        {
          name: 'Steve Smith',
          email: 'ssmith@gmail.com',
          contacted: false,
        },
        {
          name: 'Tom White',
          email: 'twhite@gmail.com',
          contacted: false,
        },
      ],
    };
  },
  methods: {
    addUser: function addUser(e) {
      this.users.push({
        name: this.newUser.name,
        email: this.newUser.email,
        contacted: false,
      });
      e.preventDefault();
    },
  },
};
</script>

<style scoped>
    
</style>