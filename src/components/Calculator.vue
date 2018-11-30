// note: 7 mins in. 
// https://www.youtube.com/watch?v=m1_ih43p24s

<template>
  <div class="calculator">
    <!-- <h1>Calculator</h1> -->
    <div class="display">{{current || 0}}</div>
    <div class="btn" @click="clear">C</div>
    <div class="btn">+/-</div>
    <div class="btn">%</div>
    <div class="btn">/</div>
    <div class="btn" @click="append('7')">7</div>
    <div class="btn" @click="append('8')">8</div>
    <div class="btn" @click="append('9')">9</div>
    <div class="btn">*</div>
    <div class="btn" @click="append('4')">4</div>
    <div class="btn" @click="append('5')">5</div>
    <div class="btn" @click="append('6')">6</div>
    <div class="btn">-</div>
    <div class="btn" @click="append('1')">1</div>
    <div class="btn" @click="append('2')">2</div>
    <div class="btn" @click="append('3')">3</div>
    <div class="btn">+</div>
    <div class="btn zero">0</div>
    <div class="btn">.</div>
    <div class="btn">=</div>
  </div>
</template>

<script>
export default {
  data() {
    current: "123";
  },
  methods: {
    clear() {
      current = "";
    },
    sign() {},
    percent() {
      this.current = `${parseFloat(this.current) / 100}`;
    },
    append(num) {
      this.current = `${this.current}${num}`;
    }
  }
};
</script>

<style scoped>
.calculator {
  margin: 0 auto;
  width: 400px;
  font-size: 40px;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: minmax(50px, auto);
}
.display {
  grid-column: 1/5;
  background-color: lightskyblue;
}
.zero {
  grid-column: 1/3;
}
.btn {
  background-color: #eee;
  border: 1px solid #888;
}
</style>
