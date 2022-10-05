<template>
  <div class="menu">
    <a v-for="(nav,i) in menus" :key="i"> {{ nav }} </a>
  </div>
  <h1>원룸샵</h1>
  <div v-for="(div,i) in products" :key="i">
    <h4>{{div}}</h4>
    <p>{{ price1[i] }} 만원</p>
    <button @click="increase(i)">허위매물신고</button> <span>신고수 : {{ 신고수[i] }}</span>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      신고수 : [0,0,0],
      price1 : [50, 60, 70],
      any : '가격은아무거나',
      menus : ['Home', 'Shop', 'About'],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
    }
  },
  methods: {
    increase(index){
      this.신고수[index] ++
    },
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
