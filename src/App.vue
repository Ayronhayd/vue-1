<template>
  <input className="input" type="text" v-model="userName" placeholder="Имя" /> <br />
  <input className="input" type="password" v-model="password" placeholder="Пароль" /> <br />
  <input className="input" type="email" v-model="email" placeholder="Email" />
  <p className="error">{{ error }}</p>
  <button type="button" @click="sendData()">Отправить</button>
  <!-- <p>{{ users }}</p> -->

  <div v-if="users.length == 0">У нас нет пользователей</div>
  <div v-else-if="users.length == 1">у нас {{ users.length }} пользователь</div>
  <div v-else>У нас {{ users.length }} пользователь</div>

  <User v-for="(el, index) in users" :key="index" :user="el" :index="index" :deleteUser="deleteUser" />
</template>

<style scoped>
.input {
  margin: 10px;
  padding: 10px;
}
</style>

<script>
import User from './components/UserName.vue'

export default {
  components: { User },
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
      } else if (this.password == '') {
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
    deleteUser(index) {
      this.users.splice(index, 1)
    },
  },
}
</script>
