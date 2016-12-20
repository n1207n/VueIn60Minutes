<template>
  <div class="test">
    <input type="text" v-model="title" />
    <!-- <span v-html="title"></span> -->
    <h1>{{title}}</h1>
    <p v-if="showName">{{user.firstName}}</p>
    <p v-else>Nobody</p>
    <!-- <p v-text="user.firstName"></p> -->

    <ul>
      <li v-for="item in items">{{item.title}}</li>
    </ul>

    <button v-on:click="greet('Hello world')">Say greeting</button>
    <input type="text" v-on:keyup="pressKey" v-on:keyup.enter="enterHit"/>
    <hr>
    <br>
    <label>First Name: </label> <input type="text" v-model="user.firstName" />
    <br>
    <label>Last Name: </label> <input type="text" v-model="user.lastName" />

    <h3>{{fullName}}</h3>

    <h2>{{msg}}</h2>
  </div>
</template>

<script>
export default {
  name: 'test',
  props: {
    msg: {
      type: String,
      default: 'Foobar',
    },
  },
  data() {
    return {
      title: 'Hello world',
      user: {
        firstName: 'John',
        lastName: 'Doe',
      },
      showName: true,
      items: [
        { title: 'Item 1' },
        { title: 'Item 2' },
        { title: 'Item 3' },
      ],
    };
  },
  computed: {
    fullName: function fullName() {
      return `${this.user.firstName} ${this.user.lastName}`;
    },
  },
  methods: {
    greet: (greeting) => {
      console.log(greeting);
    },
    pressKey: (e) => {
      console.log(e.target.value);
    },
    enterHit: () => {
      console.log('You hit enter');
    },
  },
};
</script>

<style scoped>
    
</style>