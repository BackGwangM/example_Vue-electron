<template>

  <div id="number_btn">
      <div class="btn symbol" v-on:click="$EventBus.$emit('clear')">
          <span>Clear</span>
      </div>
      <div class="btn symbol">
          <span>+/-</span>
      </div>
      <div class="btn symbol">
          <span>%</span>
      </div>
      <div class="btn calc symbol">
          <span>/</span>
      </div>
      <div class="btn" v-on:click="$EventBus.$emit('click-num',7)">
          <span>7</span>
      </div>
      <div class="btn" v-on:click="$EventBus.$emit('click-num',8)">
          <span>8</span>
      </div>
      <div class="btn" v-on:click="$EventBus.$emit('click-num',9)">
          <span>9</span>
      </div>
      <div class="btn calc symbol">
          <span>×</span>
      </div>
      <div class="btn" v-on:click="$EventBus.$emit('click-num',4)">
          <span>4</span>
      </div>
      <div class="btn" v-on:click="$EventBus.$emit('click-num',5)">
          <span>5</span>
      </div>
      <div class="btn" v-on:click="$EventBus.$emit('click-num',6)">
          <span>6</span>
      </div>
      <div class="btn calc symbol">
          <span>-</span>
      </div>
      <div class="btn" v-on:click="$EventBus.$emit('click-num',1)">
          <span>1</span>
      </div>
      <div class="btn" v-on:click="$EventBus.$emit('click-num',2)">
          <span>2</span>
      </div>
      <div class="btn" v-on:click="$EventBus.$emit('click-num',3)">
          <span>3</span>
      </div>
      <div class="btn calc symbol">
          <span>+</span>
      </div>
      <div class="btn" v-on:click="$EventBus.$emit('click-num','00')">
          <span>00</span>
      </div>
      <div class="btn" v-on:click="$EventBus.$emit('click-num',0)">
          <span>0</span>
      </div>
      <div class="btn symbol" v-on:click="$EventBus.$emit('click-num','.')">
          <span>.</span>
      </div>
      <div class="resultbtn">
          <div id="result">=</div>
      </div>
  </div>
</template>
<script>

export default {
  
}
</script>
<style scoped>
    #number_btn{
        position: relative;
        left: 2.5vw;
        width: 95vw;
        height: 59vh;
    }
    .btn{
        display: flex;
        justify-content: center;
        align-items: center;
        width: 25%;
        height: 25%;
        float: left;
        font-size: 5vmin;
        border-radius: 10px;
        cursor: pointer;
        color: #555555;
    }
    .resultbtn{
        display: flex;
        justify-content: center;
        align-items: center;
        width: 25%;
        height: 25%;
        float: left;
        font-size: 5vmin;
        border-radius: 10px;
        cursor: pointer;
        color: #555555;
    }
    .btn:hover{
        background-color: #DDDDDD;
        animation-name: focus;
        animation-duration: 0.25s;
    }
    .btn:click{
        background-color: #DDDDDD;
    }
    .symbol{
        font-weight: 700;
        color: black;
    }
    .calc{
        color: #EE4444;
    }
    #result{
        text-align: center;
        line-height: 10vmin;
        color: #FFFFFF;
        background-color: #EE4444;
        border-radius: 10vmin;
        font-size: 5vmin;
        width: 10vmin;
        height: 10vmin;
        box-shadow: 3px 3px 30px 2px #EE4444;
    }
    #result:hover{
        animation-name: result_focus;
        animation-duration: 0.25s;
        background-color: #DD2222;
    }
    @keyframes result_focus{
        from{
            background-color: #EE4444;
        }
        to{
            background-color: #DD2222;
        }
    }
    @keyframes focus{
        from{
            background-color: #FFFFFF;
        }
        to{
            background-color: #DDDDDD;
        }
    }

    
</style>

