<template>
  <div class="todo-item" v-bind:class="{ 'is-completed': todo.completed }">
    <table>
      <tr>
        <td>
          <input type="checkbox" @change="markComplete" />
        </td>
        <td>
          {{ todo.title }}
        </td>
        <td>
          <button @click="$emit('del-todo', todo.id)">delete</button>
        </td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    },
  },
};
</script>

<style scoped>
.is-completed {
  -webkit-text-decoration-line: line-through; /* Safari */
  text-decoration-line: line-through;
}
</style>
