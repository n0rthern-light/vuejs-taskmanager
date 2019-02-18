<template>
  <div class="container">
    <span class="title">Your tasks..</span>
    <div v-for="todo in todos" :key="todo.id">
      <TodoItem :todo="todo" v-on:del-todo="$emit('del-todo', todo.id)" v-on:update-array="$emit('update-array', todo)"/>
    </div>
  </div>
</template>

<script>
import TodoItem from './TodoItem.vue';

export default {
  components: {
    TodoItem
  },
  name: 'Todos',
  props: ['todos']
}
</script>

<style scoped>
.container {
  padding: 10px;
  background-color: #eee;
  border-radius: 10px;
  margin: 30px auto 0 auto;
  width: 80%;
  max-width: 768px;
  display: flex;
  flex-direction: column;
}

.container .title {

}

.container div {
  flex: 1;
}
</style>
