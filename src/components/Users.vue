<template>
  <div class="users">
    <h1>Users</h1>

    <ul>
      <li v-for="user in users">
        <input type="checkbox" class="toggle" v-model="user.contacted" />
        <span :class="{contacted: user.contacted}">{{user.name}}: {{user.email}}</span>
        <button v-on:click="deleteUser(user)">X</button>
      </li>
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
    deleteUser: function deleteUser(user) {
      this.users.splice(this.users.indexOf(user), 1);
    },
  },

  created: function created() {
    this.$http.get('https://jsonplaceholder.typicode.com/users')
      .then((response) => {
        console.log(response.data);
        this.users = response.data;
      }, (response) => {
        console.log(response.data);
      });
  },
};
</script>

<style scoped>
    .contacted {
      text-decoration: line-through;
    }
</style>