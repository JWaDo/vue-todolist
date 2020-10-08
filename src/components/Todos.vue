<template>
  <div>
    <div v-for="todo in todos" :key="todo.id">
      <Todo :todo="todo" />
    </div>
  </div>
</template>

<script>
import Todo from "./Todo";

export default {
  name: "Todos",
  components: {
    Todo,
  },
  props: {
    todos: Array,
  },
};
</script>

<style scoped>
</style>