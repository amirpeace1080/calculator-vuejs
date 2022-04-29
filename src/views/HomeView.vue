<template>
  <div id="app">
    <div class="container">
      <div class="calculator">
        <div class="answer">{{ str }}</div>
        <!-- <div class="display">{{ str + current }}</div> -->
        <div @click="clear" id="clear" class="btn operator">C</div>
        <div @click="append('+/-')" id="sign" class="btn operator">
          +/-
        </div>
        <div @click="append('%')" id="percent" class="btn operator">
          %
        </div>
        <div @click="append('/')" id="divide" class="btn operator">
          /
        </div>
        <div @click="append(7)" id="n7" class="btn">7</div>
        <div @click="append(8)" id="n8" class="btn">8</div>
        <div @click="append(9)" id="n9" class="btn">9</div>
        <div @click="append('*')" id="times" class="btn operator">*</div>
        <div @click="append(4)" id="n4" class="btn">4</div>
        <div @click="append(5)" id="n5" class="btn">5</div>
        <div @click="append(6)" id="n6" class="btn">6</div>
        <div @click="append('-')" id="minus" class="btn operator">
          -
        </div>
        <div @click="append(1)" id="n1" class="btn">1</div>
        <div @click="append(2)" id="n2" class="btn">2</div>
        <div @click="append(3)" id="n3" class="btn">3</div>
        <div @click="append('+')" id="plus" class="btn operator">
          +
        </div>
        <div @click="append(0)" value="0" id="n0" class="zero">0</div>
        <div @click="append('.')" id="dot" class="btn">.</div>
        <div @click="result" id="equal" class="btn operator">=</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HomeView",
  data() {
    return {
      str: "",
    };
  },
  methods: {
    append(param) {
      this.str += param;
    },
    result() {
      this.str = eval(this.str)
    },
    clear() {
      this.str = null;
    },
  },
};
</script>


<style scoped>
@import url("https://fonts.googleapis.com/css?family=Poppins:300,500&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

::selection {
  background: none;
}

body {
  background-color: #3fa9fc;
}

#app {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100vh;
  width: 100vw;
}

.calculator {
  display: grid;
  grid-template-rows: repeat(7, minmax(60px, auto));
  grid-template-columns: repeat(4, 60px);
  grid-gap: 12px;
  padding: 35px;
  font-family: "Poppins";
  font-weight: 300;
  font-size: 18px;
  background-color: #ffffff;
  border-radius: 10px;
  box-shadow: 0px 3px 80px -30px rgba(13, 81, 134, 1);
}

.btn,
.zero {
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  text-align: center;
  text-decoration: none;
  outline: none;
  color: #484848;
  background-color: #f4faff;
  border-radius: 5px;
}

.display,
.answer {
  grid-column: 1 / 5;
  display: flex;
  align-items: center;
}

.display {
  color: #a3a3a3;
  border-bottom: 1px solid #e1e1e1;
  margin-bottom: 15px;
  overflow: hidden;
  text-overflow: clip;
}

.answer {
  font-weight: 500;
  color: #146080;
  font-size: 55px;
  height: 65px;
}

.zero {
  grid-column: 1 / 3;
}

.operator {
  background-color: #d9efff;
  color: #3fa9fc;
}
</style>