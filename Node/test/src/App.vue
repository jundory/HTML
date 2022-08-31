<template>

<div class="black-bg" v-if="모달창 == true">
  <div class="white-bg">
    <h4> 상세페이지 </h4>
      <p> 내용 </p>
      <button @click="모달창 = false">닫기</button>
  </div>
</div>

<div class="menu" >
  <a v-for = "jun in menu" :key = "jun">  {{jun}} </a>
  </div>

  <!-- for 반복
  <div v-for = "(a, i) in products" :key="i">
    <h4> {{a}}</h4>
    <p> 50 만원</p>
    <button @click="신고수++">허위매물신고</button> <span>신고 수 : {{신고수}}</span>
</div>
ㄴ -->


  <div>
    <img :src="room[0].image" class="room-img">
    <h4> {{room[0].title}}</h4> 
    <p> {{room[0].price}}원</p>
    <button @click="increase()">허위매물신고</button> 
    <span>신고 수 : {{신고수}}</span>
</div>
  <div>
    <img src="./assets/room1.jpg" class="room-img">
    <h4> {{products[1]}}</h4>
    <p> 50 만원</p>
    <button @click="increase()">허위매물신고</button>
     <span>신고 수 : {{신고수}}</span>
</div>
  <div>
    <img src="./assets/room2.jpg" class="room-img">
    <h4> {{products[2]}}</h4>
    <p> 50 만원</p>
    <button @click="increase()">허위매물신고</button>
     <span>신고 수 : {{신고수}}</span>
</div>

  
</template>

<script>
import data from './assets/room.js';

export default {
  name: 'App',
  data(){
    return {
      room : data,
      모달창 : false,
      menu : ['home', 'shop', 'about'],
      products : ["역삼동 원룸", "천호동 원룸", "마포구 원룸"],
      신고수 : 0,
    }
  },

  methods : { 
    increase(){
      this.신고수 ++;
    }
  },

  components: {
  }
}



</script>

<style>

body {
margin: 0;
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%; height: 100%;
  background : rgba(0,0,0,0,5);
  position: fixed; padding: 20px;
}

.white-bg {
  width: 100%;
  background : white;
  border-radius: 8px;
   padding: 20px;
}

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
  color : white;
  padding : 10px;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}


</style>
