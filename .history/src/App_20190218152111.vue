<template>
  <div id="app">
    <h3>{{msg}}</h3>
    <Todos :todos="todos" v-on:del-todo="delTodo" v-on:update-array="updateArr"/>
  </div>
</template>

<script>

import Todos from '@/components/Todos.vue';

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
          completed: true
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
    sortByCompleted() {
      this.todos = this.todos.sort((a,b)=> a-b);
    },
    delTodo(id) {
      this.todos = this.todos.filter((el) => el.id !== id);
    },
    updateArr(obj) {
      this.todos.map((el) => el.id === obj.id ? obj : el);
      this.sortByCompleted();
    }

  },
  mounted() {
    this.todos.sort((a, b) => a.completed - b.completed)
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
