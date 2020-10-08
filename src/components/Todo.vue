<template>
  <div class="todoContainer">
    <input type="checkbox" name="completed" v-model="checked" />
    <p :class="checked ? 'done' : 'todo'">{{ todo.title }}</p>
  </div>
</template>

<script>
export default {
  name: "Todo",
  props: {
    todo: Object,
  },
  data: function () {
    return {
      checked: this.$props.todo.completed,
    };
  },
};
</script>

<style scoped>
.todoContainer {
  display: flex;
  justify-content: center;
  align-items: center;
}

.done {
  text-decoration: line-through;
  color: red;
}

.todo {
  color: green;
}
</style>