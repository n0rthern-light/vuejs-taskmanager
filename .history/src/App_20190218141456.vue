<template>
  <div id="app">
    <h3>{{msg}}</h3>
    <Todos />
  </div>
</template>

<script>

import Todos from '@/components/Todos';

export default {
  name: 'app',
  components: {
    Todos
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: 'Todo #1',
          completed: false
        },
        {
          id: 2,
          title: 'Todo #2',
          completed: false
        },
        {
          id: 3,
          title: 'Todo #3',
          completed: false
        },
        {
          id: 4,
          title: 'Todo #4',
          completed: false
        }
      ],
      msg: ''
    }
  },
  methods: {
    /* eslint-disable */

  },
  mounted() {
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
