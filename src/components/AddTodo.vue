<template>
  <div>
    <form v-on:submit="handleSubmit">
      <input
        type="text"
        name="title"
        v-model="title"
        placeholder="Enter A Todo"
      />
      <input type="submit" value="Add TODO" />
    </form>
  </div>
</template>

<script>
import { v4 } from "uuid";
export default {
  name: "AddTodo",
  data() {
    return {
      title: "",
    };
  },
  methods: {
    handleSubmit(e) {
      e.preventDefault();
      if (this.title === null || this.title === "") {
        return alert("Please Enter A Todo");
      }
      const newTodo = {
        id: v4(),
        title: this.title,
        completed: false,
      };
      this.$emit("add-todo", newTodo);
      this.title = "";
    },
  },
};
</script>

<style scoped>
form {
  display: flex;
}
input[type="text"] {
  flex: 10;
  padding: 5px;
}
</style>
