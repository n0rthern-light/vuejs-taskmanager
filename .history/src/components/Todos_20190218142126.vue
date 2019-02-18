<template>
  <div>
    <div v-for="todo in todos" :key="todo.id">
      {{todo.title}}
    </div>
  </div>
</template>

<script>
import TodoItem from '@/components/TodoItem';

export default {
  name: 'Todos',
  props: ['todos']
}
</script>

<style scoped>

</style>
