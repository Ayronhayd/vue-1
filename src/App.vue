<template>
  <h1>{{ info }}</h1>
  <p>{{ someInfo }}</p>

  <button type="button" @click="userData()">сообщения</button>
</template>

<style scoped>
h1 {
  color: green;
  text-align: center;
}

p {
  color: red;
  text-align: center;
}
</style>

<script>
export default {
  data() {
    return {
      info: 'Title',
      someInfo: 'Some info',
    }
  },
  methods: {
    userData() {
      this.info = 'New title'
      this.someInfo = 'New info'
    }
  }
}
</script>
