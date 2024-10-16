<script>
import {message,reversedMessage} from '../key';
export default{

  inject: {
      customMessage : {
        from: message,      //import로 불러온 symbol값
        default: 'default hello!',
      },

      customReversedMessage : {
        from: reversedMessage,
        default: 'default hello!',
      },
  },

  // inject:['message','reversedMessage'],

// data(){
//   return {
//     number : 10,

//   };
// },
// computed : {
//   doubleNum(){
//     return this.number *2;

//   }
// },
// methods : {
//   increment(){
//     this.number++;
//   },
// },
};
</script>

<template>
  <!-- <h1>컴포넌트</h1>
  <p>First Component</p> -->

<!-- <h1> {{ message }}</h1>
<h1>{{ reversedMessage }}</h1>  -->

<h1> {{ custoMessage }}</h1>
<h1>{{ customReversedMessage }}</h1> 
</template>

<style scoped>
h1 {
  color: red;
}

p{
  color: orangered;
}

</style>
