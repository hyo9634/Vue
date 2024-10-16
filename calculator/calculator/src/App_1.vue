<script>
export default {
  data() {
      return {
        output: null,   //화면에 입력되는 부분
        prev: null,     //이전에 입력된 값을 저장
        cur: null,      //현재 입력된 값을 저장
        operator: null, //연산자 저장
        operatorActions: {  //사칙 연산을 수행하는 함수를 각각 객체로 정의한다.(swich case문 객체)
            '+' : (n1, n2) => n1 + n2,
            '-' : (n1, n2) => n1 - n2,
            '*' : (n1, n2) => n1 * n2,
            '/' : (n1, n2) => n1 / n2,
        },
      }
  },

  methods :{
    // //operation()함수에서는 console객체의 log()메서드를 사용해 ‘click’을 출력하게 하기
    // operation(){
    // console.log("click");

    //초기화 로직 c부분을
                clear() {
                      this.output = null;
                      this.prev = null;
                      this.cur = null;
                      this.operator = null;
                      return;
                  },


    calculate(number){
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
                  if (this.operator != null){
                    //opseratorActions로 switch 리팩토링 ,  객체의 각 속성은 함수를 값으로 가지는 메서드

                    this.prev = this.operatorActions[this.operator](this,pre,this.cur);

                    //등호면 연산 결과 렌더링한다.

                    this.cur = Number(this.cur);
                      if(this.operator != null) {
                          switch (this.operator) {
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

    };
  },

    //연산 흐름을 제어
    userInput(number){
            //사용자가 입력한 숫자(문자열) 저장 -> 수식이 누적됨
            this.cur = this.cur === null ? number: (this.cur += number);
      //입력한 값이 출력칸에 표시되도록 output 데이터에 저장
      this.output = this.cur;

    },

      //클릭한 버튼 값 가져오기
    operation(e){
      //<input>태그에 대한 value속성 값을 이벤트 객체가 가져와 출력하게 하는 작성하기
      const number = e.currentTarget.value;
      console.log(number,e);
      if(number === 'C'){
        this.clear();
      } else if (['+','-','*','/','='].includes(number)) {
        this.calculate(number);
      } else {
        this.userInput();
      }
    },
    }
  }
</script>

<template>
  <div class="calculator">
    <form name="forms">
      <input v-model="output" type="text" name="output" readonly />
      <input type="button" class="clear" value="C" @click="operation" />
      <input type="button" class="operator" value="/" @click="operation" />
      <input type="button" value="1" @click="operation" />
      <input type="button" value="2" @click="operation" />
      <input type="button" value="3" @click="operation" />
      <input type="button" class="operator" value="*" @click="operation" />
      <input type="button" value="4" @click="operation" />
      <input type="button" value="5" @click="operation" />
      <input type="button" value="6" @click="operation" />
      <input type="button" class="operator" value="+" @click="operation" />
      <input type="button" value="7" @click="operation" />
      <input type="button" value="8" @click="operation" />
      <input type="button" value="9" @click="operation" />
      <input type="button" class="operator" value="-" @click="operation" />
      <input type="button" class="dot" value="." @click="operation" />
      <input type="button" value="0" @click="operation" />
      <input
        type="button"
        class="operator result"
        value="="
        @click="operation"
      />
    </form>
  </div>
</template>

<style>
@import "./style.css";
</style>
