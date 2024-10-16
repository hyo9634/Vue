<script>
    export default {
      data(){
        return{
          number : 0,

        };
      },

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
  <button type="text" @keyup.enter="(&event)="onKeyupHandler1"/>
  <h1>{{number}}</h1>
  <button type ="button"
</template>
<style>


</style>