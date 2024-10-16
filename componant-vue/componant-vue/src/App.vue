<script>
import FirstChildCopy from './components/FirstChild copy.vue';
import UserProfile from './components/UserProfile.vue';
//provide 속성의 키를 symbol값으로 사용하여 데이터 주입
import {message,reversedMessage} from '@/key.js';

export default {

  components : {
    FirstChildCopy,
  },
  provide() {
    return {
      [message]: this.message,
      [reversedMessage] : this.reversedMessage,
      //심볼의 키를 이용하기 위해 [] 사용
    }
  },

  data(){
    return {
      message: 'Hello FirstChild Component!'
    }
  },
  computed :{
    reversedMessage() {
      return this.message.split('').reverse().join('');
    }
  }
  //컴포넌트에 이벤트 걸기
  // methods: {
  //   printHello(name,age){  
  //     alert(`${name}, ${age}`);
  //   },
  // },

  // data() {
  //   return {
  //     name : '김', };
  // },

}
  

</script>

<template>
<!--//dom1이랑 연결하기
<h1 ref="dom1">h1 태그</h1> //마운드 된 후에 참조 할 수 있다. 돔에 대한 참조 속성이 설정되어있지 않기 때문에-->
<!--:age 컴포넌트 사용자 정의 속성을 v-bind (:)로 바인딩 할 수 있다.-->
<!-- <UserProfile :name="name"/> -->
<!-- <UserProfile @print-hello="(name,age)=>printHello(name,age)"/> -->
<FirstChildCopy/>
</template>


<style>


h1 {
  color: rgb(193, 255, 142);
}

p {
  color: rgb(196, 168, 222); 
}

</style>
