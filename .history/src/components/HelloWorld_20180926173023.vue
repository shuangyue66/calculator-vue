<template>
  
    <div class="button-wrap">
        <p id="asd" class="input-num">0</p>
        <button class="common-button nc">c</button>
        <button class="common-button n03" >+/-</button>
        <button class="common-button n13">%</button>
        <button class="common-button n÷">÷</button>
        <button class="common-button n7">7</button>
        <button class="common-button n8" >8</button>
        <button class="common-button n9">9</button>
        <button class="common-button n×">×</button>
        <button class="common-button n4">4</button>
        <button class="common-button n5">5</button>
        <button class="common-button n6" >6</button>
        <button class="common-button n23">-</button>
        <button class="common-button n1">1</button>
        <button class="common-button n2">2</button>
        <button class="common-button n3">3</button>
        <button class="common-button n33">+</button>
        <button class="common-button n0">0</button>
        <button class="common-button nq">.</button>
        <button class="common-button n10">=</button>
    </div>

</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data: () => {
    showNum = 0, // 显示的数字
    operationNum = 0, // 运算后的答案
    jkl = 0,
    nowname = document.getElementsByClassName("common-button"),
    nowLen =  nowname.length,
    lastEnterBtn = '',
    dengyujia = 0,
    // for (var i = 0; i < nowLen; i++) {
      
    // }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.button-wrap {
    width: 540px;
    height: 960px;
    padding-left: 5px;
    background-color: black;
    margin: auto;
   
}

.input-num {
    color: #fff;
    padding: 183px 25px 0 0;
    font-size: 88px;
    height: 88px;
    line-height: 88px;  
    text-align: right;
    margin: 0px;
}

.common-button {
    background-color: #343434;
    border-color: black;
    width: 111px;
    height: 111px;
    color: #fefefe;
    font-size: 48px;
    border-radius: 100%;
    margin: 0 0 18px 18px;
    float: left;
    text-align: center;
    transition: background-color .5s, color .5s;
}



.n÷, .n10, .n23, .n33, .n× {
    background-color: #f19a39;
    color: #ffffff;
    /* margin-right: 0px; */
}

.nc, .n03, .n13 {
    background-color: #a6a6a6;
    color: black;
}
.n0 {
    width: 241px;
    height: 111px;
    border-radius: 60px;
    text-align: left;
    padding-left: 42px;
}
.nc, .n03, .n13, .n÷ {
    margin-top: 40px;
}
button:hover{
     background-color: rgba(255,255,255,0.9) ;
     color: black;
}
</style>
