<template>
  <input type="text" v-model="userName" placeholder="Имя" />
  <input type="password" v-model="password" placeholder="Пароль" />
  <input type="email" v-model="email" placeholder="Email" />
<p className="error">{{ error }}</p>
  <button type="button" @click="sendData()">Отправить</button>

  <p>{{ users }}</p>
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
