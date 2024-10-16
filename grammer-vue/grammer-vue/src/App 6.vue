(예제) keyup 이벤트로 enter키(13) 입력을 확인하면 별도의 동작을 취하도록 코드 작성
<script>
    export default {
        methods: {
        clickhandler(event){
        if(event.keyCode == 13) {
          alert("enter키 눌림");
          }
        },
        onKeyupHandler1(){
        consle.log("enter키 눌림");
          },
        }

        }

</script>

<!-- mustach syntax -->
<template>
  <button type="text" @keyup="(&event) => onKeyupHandler($event)"/>
  <button type="text" @keyup.enter="(&event) => "onKeyupHandler1"/>
</template>
<style>


</style>