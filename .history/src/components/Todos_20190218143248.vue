<template>
  <div>
    <div v-for="todo in todos" :key="todo.id">
      <TodoItem :todo="todo"/>
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
  props: ['todos'],
  mounted() {
    //this.todos.sort((a, b) => a.completed - b.completed)
  }
}
</script>

<style scoped>

</style>
