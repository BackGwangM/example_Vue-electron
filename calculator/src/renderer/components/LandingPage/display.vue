<template>
  <div id="display">
      <div id="Formula">
          {{formula}}
      </div>
      <div id="number">
          {{num}}
      </div>
  </div>
</template>
<script>
var formula = null;
export default {
  data(){
      name: 'display'
      return{
        formula : '',
        num: '',
        sign: '',
        check: 0
      };
  },
      created() {
      this.$EventBus.$on('click-num', (num) => {
          this.num = this.num+num;
          if(num == '.' || num == '0' && this.check == 0){
              return;
          }
        else{
            this.num = this.num * 1;
            this.num = String(this.num);
        }
      });
      this.$EventBus.$on('clear', () => {
        this.formula = '';
        this.num = '';
        this.check = 0;
      });
      this.$EventBus.$on('backspace', ()=>{
          if(this.check == 0){
              this.num = this.num.substring(0, this.num.length - 1);
          }
          
      })
      this.$EventBus.$on('sign-switch', ()=> {
          if(this.check == 0){
            this.num = this.num * -1;
            this.num = String(this.num);
          }
        
      })
      this.$EventBus.$on('calc', (sign)=> {
          if(this.num != '' && this.check == 0){
            this.formula = this.formula + ' '+ this.num + ' '+sign;
            this.num = '';
          }
          else if(this.num != ''){
            this.formula = this.num + ' '+sign;
            this.num = '';
            this.check = 0;
          }
      })
      this.$EventBus.$on('result', ()=> {
          if(this.num != '' && this.check == 0){
            this.check = 1;
            formula = this.formula+ ' ' + this.num;
            this.formula = formula + ' = ';
            formula = formula.replace('×','*');
            formula = formula.replace('÷','/');
            formula = formula.replace(' ','');
            console.log(formula);
            this.num = eval(formula);
          }
      })
    }
}
</script>
<style>
#display{
    position: relative;
    top: 5vh;
    left: 5vw;
    width: 85vw;
    
}
#Formula{
    height: 7.5vh;
    width: 100%;
    color: #555555;
    font-size:6vmin;
    text-align: right;
}
#number{
    height: 17.5vh;
    line-height: 17.5vh; 
    width: 100%;
    color: #000000;
    font-size:10vmin;
    text-align: right;
    border: 0;
    ime-mode:inactive;
}
</style>
