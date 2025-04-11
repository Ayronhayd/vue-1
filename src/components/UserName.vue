<template>
  <!-- без :key="index" не работает -->
  <div className="user">
    <button @click="deleteUser(index)">Удалить</button>
    <p>{{ user.userName }}</p>
    <p>{{ user.password }}</p>
    <p>{{ user.email }}</p>
  </div>
</template>

<script>
export default {
  props: {
    user: {
      type: Object,
      required: true,
    },
    index: {
      type: Number,
      required: true,
    },
    deleteUser: {
      type: Function,
      required: true,
    },
  },
}
</script>

// scoped позволяет ограничить стили внутри компонента
<style scoped>
.user {
  background-color: aqua;
  border: 1px solid black;
  width: 500px;
  margin: 0 auto;
  text-align: center;
  margin-bottom: 20px;
}

button {
  background-color: red;
  border: none;
  padding: 10px;
  margin: 10px;
}
</style>
