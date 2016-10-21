<template>
  <div id="Hello">
    Num1:<input type="text" v-model="num1"><br>
    Num2:<input type="text" v-model="num2"><br>
    <button @click="add()">+</button>
    <button @click="del()">-</button>
    <button @click="kun()">x</button>
    <button @click="hard()">/</button>
    <button @click="cancle()">C</button><br>
    Sum  :<input type="text" v-model='sum' disabled>
  </div>
</template>

<script>
export default {
  methods: {
    add: function () {
      // let data = {}
      this.user.push({
        num1: this.num1,
        num2: this.num2
      })
      this.sum = parseInt(this.num1) + parseInt(this.num2)
    },
    del: function () {
      this.sum = parseInt(this.num1) - parseInt(this.num2)
    },
    kun: function () {
      this.sum = parseInt(this.num1) * parseInt(this.num2)
    },
    hard: function () {
      this.sum = parseInt(this.num1) / parseInt(this.num2)
    },
    cancle: function () {
      this.num1 = ''
      this.num2 = ''
    }
  },
  data () {
    return {
      sum: 0,
      num1: '',
      num2: '',
      user: []
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
