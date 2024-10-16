<script>
    export default {
        data : function(){
              return {
                
                  name : '신세계',
                  gender : 'male',
                  age: 20
                  }
              }
        }

</script>

<!-- mustach syntax -->
<template>
  <div v-memo ="[name,gender,age]">
    <p>이름 : {{name}}</p>
    <p>성별 : {{gender}}</p>
    <p>나이 : {{age}}</p>
  </div>

  <button type="button" @click="name ='수정'">이름변경</button>
  <button type="button" @click="gender ='female'">성별변경</button>
  <button type="button" @click="age =22">나이변경</button>


</template>
<style>
    .blue-color {
      color: blue;
    }
</style>