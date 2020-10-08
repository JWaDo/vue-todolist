<template>
  <div>
    <h1>My awesome todo list with Vue</h1>
    <TodoForm @added-todo="addedTodo" />
    <Todos :todos="todos" />
  </div>
</template>

<script>
import Todos from "./Todos";
import TodoForm from "./TodoForm";

export default {
  name: "TodoList",
  components: {
    Todos,
    TodoForm,
  },
  data: function () {
    return {
      todos: [],
    };
  },
  methods: {
    addedTodo: function (todo) {
      this.$data.todos = [todo, ...this.$data.todos];
    },
  },
  mounted: function () {
    fetch("https://jsonplaceholder.typicode.com/todos")
      .then((data) => data.json())
      .then((todos) => (this.$data.todos = todos));
  },
};
</script>

<style scoped>
</style>>