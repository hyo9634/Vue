<script>
import FirstChild from './components/FirstChild.vue'; //1. firstchild라는 컴포넌트를 지역등록하기 위해 불러온다.

export default {
  beforeCreate() {
    console.log('beforecrate');
  },
  created(){
    setTimeout(()=>{
      this.visible = false; 
      //컴포넌트가 생성된 후 3초 뒤에 visible 데이터 값을 false FirstChild의 스크립트를 실행하고 돔이 제거되고 update()된 후, 마운트된 상태로 돌아감 
    }, 3000);
  },
  beforeMount(){
    console.log('beforeMount');
  },
  mounted(){
    console.log('mounted');
  },
  beforeUpdate(){
    console.log('beforeupdate');
  },
  updated(){
    console.log('updated');
  },
  beforeUnmount(){
    console.log('beforeUnmount');
  },
  unmounted(){
    console.log('unmounted');
  },

  //컴포넌트 등록하기
  components : {
    FirstChild //2. 불러온 firstchild 컴포넌츠를 components 옵션 속성으로 지역등록
  },
  data(){
    return{
      visible: true, //3. visible 데이터 정의하고 초깃값으로 true셋팅
    }
  },

}
</script>

<template>

<FirstChild v-if="visible"/>

</template>


<style>


h1 {
  color: rgb(193, 255, 142);
}

p {
  color: rgb(196, 168, 222); 
}

</style>
