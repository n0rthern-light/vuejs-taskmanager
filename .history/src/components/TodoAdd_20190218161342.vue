<template>
  <div class="container">
    <h3>Add Task</h3>
  </div>
</template>

<script>
export default {
  name: 'TodoAdd',
  props: ['todos'],
  data () {
    return {
      title: ''
    }
  }
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
</style>
