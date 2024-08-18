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

  <div v-for="(rooms, i) in rooms" :key="i">
    <h4> {{ rooms.product }}</h4>
    <a> {{ rooms.price }} 만원</a>
    <button @click="rooms.신고수++">허위매물신고</button> <span> 신고수 : {{ rooms.신고수 }}</span>
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
      rooms : [
        { product: '역삼동원룸', price: 70, 신고수: 0},
        { product: '천호동원룸', price: 60, 신고수: 0},
        { product: '마포구원룸', price: 50, 신고수: 0},
      ],
      메뉴들 : ['Home', 'Shop', 'About'],
    }
  },
  components: {

  },
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
