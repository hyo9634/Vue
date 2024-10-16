<script>
    export default {
        props: {
            name:{
                type: String,
                required: false,
                validator: function (value){ //로직을 검사하는 코드. 반드시 리턴 값이 ture, false여야 함.
                    return value.length > 1;
                },
                age: {
                    type: Number,
                    default: function() {
                        return 10;
                    }
                },
            },
        //사용자 정의 속성 name, company 값을 받는다.
        //라이프싸이클 훅 함수를 가지고 있음
        //유효성검사    
    },

    emits:['print-hello'],
    //메서드 핸들러 방식
    methods: {
        parentEventCall(){
                this.$emit('print-hello','ssg',20);
        },
    }
    }


</script>
<template>
    <!--1. $emit() 이러한 발신 방식 인라인 핸들러 방식-->
    <button @click="$emit('print-hello','ssg',20)">클릭</button>
    <!--2.메서드 핸들러 방식-->
    <!-- <button @click="parentEventCall">클릭</button> -->
</template>