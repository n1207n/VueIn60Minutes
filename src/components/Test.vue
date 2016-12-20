<template>
  <div class="test">
    <!-- <span v-html="title"></span> -->
    <h1>{{title}}</h1>
    <p>{{user.firstName}}</p>
    <p v-text="user.firstName"></p>
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
    };
  },
};
</script>

<style scoped>
    
</style>