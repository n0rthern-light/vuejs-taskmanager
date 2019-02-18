<template>
  <div class="container">
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
  width: 80%;
  display: flex;
  flex-direction: column;
}

.container div {
  flex: 1;
}
</style>
