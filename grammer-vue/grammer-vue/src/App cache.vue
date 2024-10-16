<script>
  export default {
      data () {
          return {
            firstName: 'hyo',
            lastName: 'lee',
          };
      },

      //v-model로 data와 method를 양방향 연결해야함

      computed: { //내부에서 데이터를 항상 참조, 한 번 참조한 데이터는 임시저장된다(chaching됨)

        fullName(){
          console.log('computed fullName');
          return `${this.lastName} ${this.firstName}`//캐싱된 값은 한 번만 실행됨.
        },
      }
  }
</script>
<template>
<h1>{{ fullName }} </h1>
</template>
<style>
</style>

