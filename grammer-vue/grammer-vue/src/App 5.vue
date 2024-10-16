<script>
    export default {
        methods: {
        clickhandler(event,message){
          console.log(event);
          console.log(message);
        },}
      }

</script>

<!-- mustach syntax -->
<template>
  <button type="button" @click="clickhandler($event, 'Hello')">클릭1</button> <!-- clickhandler의 이벤트 객체를 methods로 넘김-->
  <button type="button" @click="clickhandler($event)">클릭2</button>
  <button type="button" @click="(&event)=>clickhandler($event)">클릭3</button> 

</template>
<style>


</style>