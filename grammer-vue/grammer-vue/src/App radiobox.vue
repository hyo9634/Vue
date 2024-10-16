<script>
    export default {
        data : function(){
              return {
              gender: ['male','female'],
              };
        },

        methods: {

        printData(){
          console.log(`id: ${this.gender}`);
        },
    }
  }
</script>

<!-- mustach syntax -->
<template>
      <form id="loginForm1">
          <input type="radiobox" id="gender" v-model="gender" value="male">남자
          <input type="radiobox" id="gender" v-model="gender" value="female">여자
          <button type="button" @click="printData">확인</button>
        </form>

</template>
<style>
    .blue-color {
      color: blue;
    }
</style>