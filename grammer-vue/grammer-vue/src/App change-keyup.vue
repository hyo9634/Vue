<script>
  export default {
      data () {
          return {
            fruits: ['apple','banana','grape'],
            selectfruits: "",
            message: "",
          };
      },

      //v-model로 data와 method를 양방향 연결해야함

      methods: {
        printData(){
            console.log(`${selectfruits}원`);
        },
        updateSelectFruit(event){
          this.selectfruits=event.target.value;
        },
        onKeyupHandler(){ //event가 일어날 때 마다 동작이 일어나는 것이기 때문에 event를 받지 않아도됨
        console.log('key up event');
        },
      }
  }
</script>

<template>
  <form id = "loginForm1">
    <select v-on:change="updateSelectFruit">
    <option value="1000">사과</option>
    <option value="500">바나나</option>
    <option value="400">포도</option>
  </select>
  가격: {{ selectfruits }} 원
  </form>
  <!--keyup-->
  <br>
  <input type="text" @keyup="onKeyupHandler()"/>

</template>
<style>
</style>

