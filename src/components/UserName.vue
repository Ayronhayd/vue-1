<template>
 <!-- без :key="index" не работает -->
 <div className="user">
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
    required: true
  }
}
}

</script>


<style>
.user {
  background-color: aqua;
  border: 1px solid black;
  width: 500px;
  margin:  0 auto;
  text-align: center;
  margin-bottom: 20px;
}
</style>
