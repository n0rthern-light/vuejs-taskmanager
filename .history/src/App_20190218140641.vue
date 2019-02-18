<template>
  <div id="app">
    <h3>{{msg}}</h3>
  </div>
</template>

<script>

export default {
  name: 'app',
  components: {

  },
  data() {
    return {
      todos: [
        {

        }
      ],
      msg: ''
    }
  },
  methods: {
    init () {

    }
  },
  mounted() {
      this.msg = 'Hello world';
      console.log('hello from mounted');
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
</style>
