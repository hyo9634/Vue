<script>
  export default {
      data () {
          return {
            uid: '',
            upw: '',
            message:'',
            gender: ['male','female'],
            fruits: ['apple','banana'],
          };
      },

      methods: {
        login() {
          console.log(`id: ${this.uid}`)
          console.log(`pwd: ${this.upw}`)
          console.log(`gender: ${this.gender}`)
        },

        printData() {
          console.log(`message: ${this.message}`);
          console.log(`fruits: ${this.fruits}`)
        }
      }
  }
</script>

<template>
  <form id="/loginForm1">
    <label for="uid">ID:<input type="text" id="uid" v-model="uid"></label>
    <label for="upw">PASSWORD:<input type="password" id="upw" v-model="upw"></label>
    <input type="radio" id="gender" v-model="gender" value="male">남성
    <input type="radio" id="gender" v-model="gender" value="female">여성
    <button type="button" @click="login">login</button>
  </form>


  <form id="loginForm2">
    <textarea v-model="message"></textarea>
    <input type="checkbox" id="fruits" v-model="fruits" value="apple">사과
    <input type="checkbox" id="fruits" v-model="fruits" value="banana">바나나
    <button type="button" @click="printData">데이터출력</button>
  </form>

</template>
<style>
</style>



<script>
  export default {
      data () {
          return {
            message: '',
          };
      },

      //v-model로 data와 method를 양방향 연결해야함

      methods: {
        onSubmitHandler(e) {
          e.preventDefault(); //별도의 폼 전송 처리하겠다.
          console.log('Onsubmit Handler')
        }
      }
  }
</script>

<template>
  <form @submit="onSubmitHandler">
    <button type="submit">submit</button>
  </form>

</template>
<style>
</style>
