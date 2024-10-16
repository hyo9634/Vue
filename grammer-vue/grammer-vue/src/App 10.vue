<script>
  export default {
      data () {
          return {
            coffee: ['아메리카노','카페라떼','바닐라라떼'],
          };
      },

      //v-model로 data와 method를 양방향 연결해야함

      methods: {
        printData() {
          console.log(`id: ${this.coffee}`);
        }
      }
  }
</script>

<template>
  <form id = "loginForm1">
    <select>
      <option id="아메리카노">아메리카노</option>
      <option id="카페라떼">카페라떼</option>
      <option id="바닐라라떼">바닐라라떼</option>
    </select>
    <button type="button">어떤 커피를 선택할까요?</button>
  </form>

</template>
<style>
</style>