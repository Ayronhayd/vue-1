<template>
  <input type="text" v-model="userName" placeholder="Имя" />
  <input type="password" v-model="password" placeholder="Пароль" />
  <input type="email" v-model="email" placeholder="Email" />
<p className="error">{{ error }}</p>
  <button type="button" @click="sendData()">Отправить</button>
  <!-- <p>{{ users }}</p> -->

  <!-- без :key="index" не работает -->
  <div v-for="(el, index) in users" :key="index">
    <p>{{ el.name }}</p>
    <p>{{ el.password }}</p>
    <p>{{ el.email }}</p>
  </div>


  <div v-if="users.length == 0">
    У нас нет пользователей
  </div>
  <div v-else-if="users.length == 1">
    у нас {{ users.length }} пользователь
  </div>
  <div v-else>
    У нас {{ users.length }} пользователь
  </div>
</template>

<style scoped></style>

<script>
export default {
  data() {
    return {
      users: [],
      error: '',
      userName: '',
      password: '',
      email: '',
    }
  },
  methods: {
    sendData() {
      if (this.userName == '') {
        this.error = 'Заполните все поля'
        return
      } else if (this.email == '') {
        this.error = 'Введите email'
        return
      }else if (this.password == '') {
        this.error = 'Введите пароль'
        return
      }

      this.error = ''

      this.users.push({
        userName: this.userName,
        password: this.password,
        email: this.email,
      })
    },
  },
}
</script>
