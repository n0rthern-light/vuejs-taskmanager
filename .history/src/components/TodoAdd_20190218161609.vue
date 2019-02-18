<template>
  <div class="container">
    <h3>Add Task</h3>
    <input type="text"/>
    <button class="btn" @click="$emit('add-todo', title)">Add Task</button>
  </div>
</template>

<script>
export default {
  name: 'TodoAdd',
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

.container input {
  padding: 10px;
  font-weight: 600;
}

.container .btn {
  font-size: 1.1em;
  background-color: #afceff;
  border: none;
  border-radius: 15px;
}

</style>
