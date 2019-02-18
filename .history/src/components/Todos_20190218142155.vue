<template>
  <div>
    <div v-for="todo in todos" :key="todo.id">
      <TodoItem :todo="todo"/>
    </div>
  </div>
</template>

<script>
import TodoItem from '@/components/TodoItem';

export default {
  components: 'TodoItem',
  name: 'Todos',
  props: ['todos']
}
</script>

<style scoped>

</style>
