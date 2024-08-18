<template>
  <div class="menu">
<!--    <a v-for="작명 in 몇번 반복할지">Home</a>-->
<!--    <a v-for="작명 in 3" :key="작명">Home</a>-->

<!--    메뉴들 의 개수만큼 반복된다.-->
<!--    <a v-for="작명 in 메뉴들" :key="작명">{{ 작명 }}</a>-->
<!--    i 는 0, 1, 2 처럼 변하는 고유값-->
<!--    <a v-for="(menus, i) in 메뉴들" :key="i">{{ menus }}</a>-->
    <a v-for="menus in 메뉴들" :key="menus">{{ menus }}</a>
  </div>

  <div v-for="(rooms, i) in 3" :key="i">
    <h4> {{ products[i] }}</h4>
    <a> {{ price[i] }}</a>
  </div>

<!--  <div>-->
<!--    <h4>{{ products[0] }}</h4>-->
<!--    <p> {{ price[0] }}</p>-->
<!--  </div>-->
<!--  <div>-->
<!--    <h4>{{ products[1] }}</h4>-->
<!--    <p> {{ price[1] }}</p>-->
<!--  </div>-->
<!--  <div>-->
<!--    <h4>{{ products[2] }}</h4>-->
<!--    <p> {{ price[2] }}</p>-->
<!--  </div>-->

</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      rooms : {
        products: ['역삼동원룸', '천호동원룸', '마포구원룸'],
        price: [70, 60, 50],
      },
      products: ['역삼동원룸', '천호동원룸', '마포구원룸'],
      price: [70, 60, 50],
      메뉴들 : ['Home', 'Shop', 'About'],
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
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;

}

.menu a {
  color: white;
  padding: 10px;

}
</style>
