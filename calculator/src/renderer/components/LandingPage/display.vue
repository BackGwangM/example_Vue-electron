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
export default {
  data(){
      name: 'display'
      return{
        formula : '',
        num: '',
        sign: ''
      };
  },
      created() {
      this.$EventBus.$on('click-num', (num) => {
          this.num = this.num+num;
          if(num == '.' || num == '0'){
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
      });
      this.$EventBus.$on('sign-switch', ()=> {
        this.num = this.num * -1;
        this.num = String(this.num);
      })
      this.$EventBus.$on('calc', (sign)=> {
          if(this.num != ''){
            this.formula = this.formula + this.num + ' '+sign;
            this.num = '';
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
