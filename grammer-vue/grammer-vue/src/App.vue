<script>
  export default {
      data () {
          return {
            array: [0,1,2],
            obj: {name: 'hyo'},
          };
      },

      watch: { //내부에서 데이터를 항상 참조, 한 번 참조한 데이터는 임시저장된다(chaching됨)
        arr: {
          handler(newValue, oldValue){
            console.log(`oldValue: ${oldValue}`);
            console.log(`newValue: ${newValue}`);
          },
          deep: true,
        },

        obj: {
          handler(newValue, oldValue){
            console.log(`oldValue: ${JSON.stringify(oldValue)}`);
            console.log(`newValue: ${JSON.stringify(newValue)}`);
        },
        deep: true,
  }
}
}
</script>
<template>
  <!--<h1 style="color : greenyellow; font-style: italic">{{ array }}</h1>-->
<h1>{{ array }}</h1>
<h1>{{ obj }}</h1>
<button @click="array.push(3)">배열값 추가</button>
<button @click="obj.company='ssg.com'">객체속성추가</button>
</template>

//원하는 구역에만: scoped
<style scoped> 
@import './assets/main.css';
h1 {
color : yellowgreen;
font-style: italic;
}

</style>

