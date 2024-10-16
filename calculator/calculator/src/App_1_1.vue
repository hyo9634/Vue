<script>
export default {
  data() {
      return {   
        output: null,   //화면에 입력되는 부분
        prev: null,     //이전에 입력된 값을 저장
        cur: null,      //현재 입력된 값을 저장
        operator: null, //연산자 저장
      }
  },

  methods :{
    // //operation()함수에서는 console객체의 log()메서드를 사용해 ‘click’을 출력하게 하기
    // operation(){
    // console.log("click");
    
    operation(e){
      //<input>태그에 대한 value속성 값을 이벤트 객체가 가져와 출력하게 하는 작성하기
      const number = e.currentTarget.value;
      console.log(number,e);
      if(number  === 'C'){
                      this.output = null;
                      this.prev = null;
                      this.cur = null;
                      this.operator = null;
                      return;
                  }

      if (['+','-','*','/','='].includes(number)) {
        //연산로직구현 클릭 순서 3*2=6(output에 출력)
        //입력 값이 3이라면 false가 출력 됨 배열에 없기 때문에
        if(!this.cur && !this.prev){
                    alert('숫자를 먼저 입력하세요. ');
                    return;
                  }
                  if(this.operator !== '' && !this.cur){
                    alert('사칙연산 기호를 연달아 누를 수 없습니다.');
                    return;
                  }
                  if( number === '=' && this.prev === this.cur){
                    return;
                  }  

                      this.cur = Number(this.cur);
                      if(this.operator != null){
                          switch(this.operator) {
                            case '+':
                              this.prev = this.prev + this.cur;
                              break;
                            case '-':
                              this.prev = this.prev - this.cur;
                              break;
                            case '*':
                              this.prev = this.prev * this.cur;
                              break;
                              case '/':
                              this.prev = this.prev / this.cur;
                              break;
                              
                          }

                          if(number === '='){
                            this.output = this.prev;
                            this.operator = null;
                            this.cur = this.prev;
                            } else {
                                this.output = null;
                                this.operator = number;
                                this.cur = null;
                            }

                      } else {
                        this.output = null;
                        this.operator = number;
                        this.prev = this.cur;
                        this.cur = null;
                      }
                      return;
                  }
                  
      //사용자가 입력한 숫자(문자열) 저장 -> 수식이 누적됨
      this.cur = this.cur === null ? number: (this.cur += number);
      //입력한 값이 출력칸에 표시되도록 output 데이터에 저장
      console.log(this.cur);
      this.output = this.cur;
      console.log(this.output);
      },
    },
    }
</script>

<template>
  <div class="calculator">
      <form name="forms">
        <input v-model="output" type="text" name="output" readonly />
        <input type="button" class="clear" value="C" @click="operation"/>
        <input type="button" class="operator" value="/" @click="operation"/>
        <input type="button" value="1" @click="operation"/>
        <input type="button" value="2" @click="operation"/>
        <input type="button" value="3" @click="operation"/>
        <input type="button" class="operator" value="*" @click="operation"/>
        <input type="button" value="4" @click="operation"/>
        <input type="button" value="5" @click="operation"/>
        <input type="button" value="6" @click="operation"/>
        <input type="button" class="operator" value="+" @click="operation"/>
        <input type="button" value="7" @click="operation"/>
        <input type="button" value="8" @click="operation"/>
        <input type="button" value="9" @click="operation"/>
        <input type="button" class="operator" value="-" @click="operation"/>
        <input type="button" class="dot" value="." @click="operation"/>
        <input type="button" value="0" @click="operation"/>
        <input type="button" class="operator result" value="=" @click="operation"/>
      </form>
    </div>
</template>

<style>
@import "./style.css";

</style>
