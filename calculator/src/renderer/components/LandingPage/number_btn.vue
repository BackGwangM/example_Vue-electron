<template>
  <div id="number_btn">
      <div class="btn symbol">
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
      <div class="btn">
          <span>7</span>
      </div>
      <div class="btn">
          <span>8</span>
      </div>
      <div class="btn">
          <span>9</span>
      </div>
      <div class="btn calc symbol">
          <span>×</span>
      </div>
      <div class="btn">
          <span>4</span>
      </div>
      <div class="btn">
          <span>5</span>
      </div>
      <div class="btn">
          <span>6</span>
      </div>
      <div class="btn calc symbol">
          <span>-</span>
      </div>
      <div class="btn">
          <span>1</span>
      </div>
      <div class="btn">
          <span>2</span>
      </div>
      <div class="btn">
          <span>3</span>
      </div>
      <div class="btn calc symbol">
          <span>+</span>
      </div>
      <div class="btn">
          <span>00</span>
      </div>
      <div class="btn">
          <span>0</span>
      </div>
      <div class="btn symbol">
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
        height: 60vh;
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

