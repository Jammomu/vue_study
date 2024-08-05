<template>

  <div class="black-bg" v-if="modalOpen == true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
      <button @click="modalOpen = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="menu in menus" :key="menu">{{ menu }}</a>
  </div>

  <img alt="Vue logo" src="./assets/logo.png">

  <div>
    <img src="./assets/logo.png" class="room-img">
    <h4 @click="modalOpen = true">{{ oneRooms[0].title }}</h4>
    <p>{{ oneRooms[0].price }}</p>
  </div>
  <div>
    <img src="./assets/logo.png" class="room-img">
    <h4>{{ products[1] }}</h4>
    <p>00 만원</p>
    <button @click="increase1">허위매물신고</button><span>신고수 : {{ declaration[1] }}</span>
  </div>
  <div>
    <img src="./assets/logo.png" class="room-img">
    <h4>{{ products[2] }}</h4>
    <p>00 만원</p>
    <button @click="increase2">허위매물신고</button><span>신고수 : {{ declaration[2] }}</span>
  </div>
</template>

<script>
import data from './components/oneroom.js';

export default {
  name: 'App',
  components: {
  },
  data(){
    return {
      menus : ['Home', 'products', 'About'],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      declaration : [0, 0, 0],

      modalOpen : false,
      oneRooms : data,
    }
  },
  methods: {
    increase0(){
      this.declaration[0]++;
    },
    increase1(){
      this.declaration[1]++;
    },
    increase2(){
      this.declaration[2]++;
    }
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

body {
  margin: 0;
}

div {
  box-sizing: border-box;
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

.room-img {
  width: 100%;
  margin-top: 40px;
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}
.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>
