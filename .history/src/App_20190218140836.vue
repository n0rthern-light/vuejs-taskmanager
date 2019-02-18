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
    async init () {
      await (() => {
        return new Promise(() => {
          setInterval(() => {
            this.msg = 'Hello World from Promise';
            resolve();
          }, 1000);
        });
      })();
    }
  },
  mounted() {
      init()
      /* eslint-disable */
      console.log('hello from mounted')
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
