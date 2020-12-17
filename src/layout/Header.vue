<template>
  <header>
    <h1>{{ title }}</h1>
  </header>
</template>

<script>
export default {
  name: "Header",
  props: ["title"],
};
</script>

<style scoped>
.header {
  background: #3333;
  color: #fff;
  text-align: center;
  padding: 10px;
}
</style>
