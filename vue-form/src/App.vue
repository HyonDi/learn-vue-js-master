<template>
  <form v-on:submit.prevent="submitForm">
    <div>
      <label for="username">id : </label>
      <input id="username" type="text" v-model="username">
    </div>
    <div>
      <label for="password">pw : </label>
      <input id="password" type="password" v-model="password">
    </div>
    <button type="submit">login</button>
  </form>
</template>

<script>
import axios from 'axios';

export default {
  data: function(){
    return {
      username: '',
      password: ''
    }
  },
  methods: {
    submitForm: function(){
      //event.preventDefault();// 새로고침을 막고있다.
      var url = 'https://jsonplaceholder.typicode.com/users';
      var data = {
        username: this.username,
        password: this.password
      }

      axios.post(url, data)
        .then(function(response){
          console.log(response);
        })
        .catch(function(error){
          console.log(error);
        })
      // http 프로토콜을 이용한 통신라이브러리.
      // 브라우저에서 서버로 데이터를 주고받기위한 라이브러리.
      console.log(this.username, this.password);
    }
  }
}
</script>

<style>

</style>