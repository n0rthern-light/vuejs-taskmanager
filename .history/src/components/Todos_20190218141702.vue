<template>
  <div>
    <h1>Todos</h1>
    <ul>
      <li v-for="todo in todos" v-key="todo.id">{{todo.title}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Todos',
  props: ['todos']
}
</script>

<style scoped>

</style>
