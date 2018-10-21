<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <h1>Parent: {{ pizzaName }}</h1>
    <Pizza  :pizzaName="pizzaName"
            :pizzaPrice="pizzaPrice"
            @changedName="pizzaName = $event"
            :changeFunc="changeNameToPizza"
          />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Pizza from './components/Pizza.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    Pizza
  },
  data() {
    return {
      pizzaName: 'Дон Бекон',
      pizzaPrice: 300
    }
  },
  methods: {
    changeNameToPizza() {
      this.pizzaName = 'ChickenBarbecu'
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
</style>
