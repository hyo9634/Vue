<script>
  export default {
      data () {
          return {
            inputStr : '',
          }
      },

      watch: { //내부에서 데이터를 항상 참조, 한 번 참조한 데이터는 임시저장된다(chaching됨)
        inputStr(newValue, oldValue) {
          console.log(`oldValue = ${oldValue}`);
          console.log(`newValue = ${newValue}`);
      }
  }
}
</script>
<template>
<input type="text" v-model="inputStr"/>
</template>
<style>
</style>

