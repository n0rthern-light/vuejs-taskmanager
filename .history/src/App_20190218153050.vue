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
    setCookie(cname, cvalue, exdays) {
      var d = new Date();
      d.setTime(d.getTime() + (exdays*24*60*60*1000));
      var expires = "expires="+ d.toUTCString();
      document.cookie = cname + "=" + cvalue + ";" + expires + ";path=/";
    },
    getCookie(cname) {
      var name = cname + "=";
      var decodedCookie = decodeURIComponent(document.cookie);
      var ca = decodedCookie.split(';');
      for(var i = 0; i <ca.length; i++) {
        var c = ca[i];
        while (c.charAt(0) == ' ') {
          c = c.substring(1);
        }
        if (c.indexOf(name) == 0) {
          return c.substring(name.length, c.length);
        }
      }
      return "";
    },
    delTodo(id) {
      console.log('delTodo');
      this.todos = this.todos.filter((el) => el.id !== id);
    },
    updateArr(obj) {
      console.log('updateArr');
      this.todos = this.todos.
      map((el) => el.id === obj.id ? obj : el).
      sort((a, b) => a.id - b.id).
      sort((a, b) => a.completed - b.completed);

      this.setCookie('todos', JSON.stringify(this.todos), 60)
    }

  },
  mounted() {
    console.log('mounted');
    this.todos = JSON.parse(this.getCookie('todos'));

    this.todos = this.todos.sort((a, b) => a.id - b.id).
      sort((a, b) => a.completed - b.completed);
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
