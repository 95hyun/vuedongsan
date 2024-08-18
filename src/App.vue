<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div>
    <h4>{{ products[0] }}</h4>
    <p> {{ price[0] }}</p>
  </div>
  <div>
    <h4>{{ products[1] }}</h4>
    <p> {{ price[1] }}</p>
  </div>
  <div>
    <h4>{{ products[2] }}</h4>
    <p> {{ price[2] }}</p>
  </div>

</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      products: ['역삼동원룸', '천호동원룸', '마포구원룸'],
      price: [70, 60, 50]
    }
  },
  components: {
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
