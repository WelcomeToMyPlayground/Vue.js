<template>

  <div class="black-bg" v-if="modal == true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
      <button v-on:click="modal = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="list in menu" :key="list">{{list}}</a>
  </div>
  
  <!-- 축약 -->
  <!-- <div v-for="productList in products" :key="productList">
    <h4>{{ productList }}</h4>
    <p>{{ price1 }}</p>
  </div> -->

  <div v-for="(list,i) in 원룸들" :key="i">
    <img :src="list[i].image" class="room-img"> 
    <h4 :style="스타일" @click="modal = true">{{ list[i].title }}</h4>
    <p>{{ list[i].price }}원</p>
    <button v-on:click="increase1()">허위매물신고</button>
    <span>신고수 : {{ 신고수[0] }} </span>
  </div>

  <div>
    <img :src="원룸들[1].image" class="room-img">
    <h4 :style="스타일1[1]" @click="modal = true">{{ 원룸들[1].title }}</h4>
    <p>{{ 원룸들[1].price }}원</p>
    <button @click="increase2()">허위매물신고</button>
    <span>신고수 : {{ 신고수[1] }} </span>
  </div>

  <div>
    <img :src="원룸들[2].image" class="room-img">
    <h4 @click="modal = true">{{ 원룸들[2].title }}</h4>
    <p>{{ 원룸들[2].price }}원</p>
    <button v-on:click="increase3()">허위매물신고</button>
    <span>신고수 : {{ 신고수[2] }}</span>
  </div>
  
  
  <div>
    <img :src="원룸들[3].image" class="room-img">
    <h4 @click="modal = true">{{ 원룸들[3].title }}</h4>
    <p>{{ 원룸들[3].price }}원</p>
  </div>

  <div>
    <img :src="원룸들[4].image" class="room-img">
    <h4 @click="modal = true">{{ 원룸들[4].title }}</h4>
    <p>{{ 원룸들[4].price }}원</p>
  </div>

  <div>
    <img :src="원룸들[5].image" class="room-img">
    <h4 @click="modal = true">{{ 원룸들[5].title }}</h4>
    <p>{{ 원룸들[5].price }}원</p>
  </div>






</template>

<script>
import data from './assets/oneroom.js';
import {apple,apple2} from './assets/oneroom.js';
apple;
apple2;

export default {
  name: 'App',
  data(){
    return {
      원룸들: data, // import 해온거 
      modal : false,
      신고수 : [0,0,0],
      menu : ['Home','Shop','About'],
      products : ['역삼동원룸','천호동원룸','마포구원룸'],
      스타일1 : ['color:red','color:blue','color:yellow'],
      스타일 : 'color:red',
      prices : [60,70,80],
      price2 : 70,
      price1 : 60
    }
  },
  methods:{
    increase1(){
      this.신고수[0] += 1;
    },
    increase2(){
      this.신고수[1] += 1;
    },
    increase3(){
      this.신고수[2] += 1;
    }
  },
  components:{
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
  color : white;
  padding: 10px;
}
.room-img {
  width: 100%;
  margin-top: 40px;
}
body {
  margin : 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%;
  height:100%;
  background: rgba(0,0,0,0.5);
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
