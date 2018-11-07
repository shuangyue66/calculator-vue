<template>
  <div class="hello">
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
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data: () => {

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
