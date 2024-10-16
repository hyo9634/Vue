<script>
    export default {
        data : function(){
              return {
              fruits: ['peach','apple'], //체크 true, 미체크: false
              };
        },

        methods: {

        printData(){
          console.log(`id: ${this.fruits}`);
        },
    }
  }
</script>

<!-- mustach syntax -->
<template>
      <form id="loginForm1">
          <input type="checkbox" id="fruits" v-model="fruits" value="peach">복숭아
          <input type="checkbox" id="fruits" v-model="fruits" value="apple">사과
          <button type="button" @click="printData">확인</button>
        </form>

</template>
<style>
    .blue-color {
      color: blue;
    }
</style>