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
