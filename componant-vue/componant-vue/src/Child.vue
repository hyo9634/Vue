<script>
import FirstChild from '@/components/FirstChild.vue';
import SecondChild from '@/components/SecondChild.vue';
import ThirdChild from '@/components/ThirdChild.vue';
import LocalChild from '@/components/LocalChild.vue';

//local component 등록
export default {
  components: {
    LocalChild, 
  }
}
</script>

<template>
  <FirstChild />
  <SecondChild />
  <ThirdChild />
  <LocalChild />
</template>


<style>


h1 {
  color: rgb(193, 255, 142);
}

p {
  color: rgb(196, 168, 222); 
}

</style>
