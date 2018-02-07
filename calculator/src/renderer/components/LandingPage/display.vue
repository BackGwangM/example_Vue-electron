<template>
  <div id="display">
      <div id="Formula">
          {{formula}}
      </div>
      <input type="text" id="number" maxlength="16" onkeyup="this.value=this.value.replace(/[^0-9.]/g,'')" autofocus>
  </div>
</template>
<script>
export default {
  data(){
      name: 'display'
      return{
        formula : '123456+123456'
      }
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
#number:focus{
    outline: none;
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
input[type=number]::-webkit-inner-spin-button {
  -webkit-appearance: none;
}
</style>
