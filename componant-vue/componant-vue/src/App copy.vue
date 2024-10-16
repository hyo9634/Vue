<script>
import FirstChild from '@/components/FirstChild copy.vue';

export default {

  components : {
    FirstChild,
  },
  
  mounted() {
  //   const dom1 = this.$refs.dom1; //돔 객체를 참조함
  //   const text = dom1.innerText;
  //   console.log(text);
  // }
  
  const childNum = this.$refs.child.number;
  const childDoubleNum = this.$refs.child.doubleNum;

    console.log(`메서드 호출 전 : ${childNum}`);
    console.log(`메서드 호출 전 : ${childDoubleNum}`);

    
    setTimeout(()=>{
        this.$refs.child.increment();

        const childNum = this.$refs.child.number;
      const childDoubleNum = this.$refs.child.doubleNum;
        
        console.log(`메서드 호출 후 : ${childNum}`);
        console.log(`메서드 호출 후 : ${childDoubleNum}`);
      });
    },


}
  

</script>

<template>
<!--//dom1이랑 연결하기
<h1 ref="dom1">h1 태그</h1> //마운드 된 후에 참조 할 수 있다. 돔에 대한 참조 속성이 설정되어있지 않기 때문에-->

<FirstChild ref="child"/>
</template>


<style>


h1 {
  color: rgb(193, 255, 142);
}

p {
  color: rgb(196, 168, 222); 
}

</style>
