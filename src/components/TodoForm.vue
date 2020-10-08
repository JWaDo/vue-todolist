<template>
  <div>
    <input type="text" name="todo" v-model="todo" />
    <button type="submit" @click.prevent="handleSubmit">Add</button>
  </div>
</template>

<script>
export default {
  name: "TodoForm",
  data: function () {
    return {
      todo: "",
    };
  },
  methods: {
    handleSubmit: function () {
      const todo = {
        userId: 8,
        id: Math.random() * Math.random(),
        title: this.$data.todo,
        completed: false,
      };
      this.$emit("added-todo", todo);
    },
  },
};
</script>

<style scoped>
</style>