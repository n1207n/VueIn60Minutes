<template>
  <div class="test">
    <!-- <span v-html="title"></span> -->
    <h1>{{title}}</h1>
    <p v-if="showName">{{user.firstName}}</p>
    <p v-else>Nobody</p>
    <!-- <p v-text="user.firstName"></p> -->

    <ul>
      <li v-for="item in items">{{item.title}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'test',
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
};
</script>

<style scoped>
    
</style>