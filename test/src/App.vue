<template>  
 
 <!-- 모달창, 상세페이지 원본
  <div class="black-bg" v-if="modal == true">
    <div class="white-bg">
      <Discount/>
      <img :src="원룸들[누른거].image" style="width:100%">
      <h4>{{ 원룸들[누른거].title}}</h4>
      <p>상품 설명 : {{ 원룸들[누른거].content}}</p>
      <p>가격 : {{ 원룸들[누른거].price }}원</p>
      <button v-on:click="modal = false">닫기</button>
    </div>
  </div>
   -->

  <!-- 컴포넌트 -->
  <Modal @closeModal="modal = false" :원룸들="원룸들" :누른거="누른거" :modal="modal"/>

  <div class="menu">
    <a v-for="list in menu" :key="list">{{list}}</a>
  </div>
  
  <!-- 컴포넌트 -->
  <Discount v-bind="오브젝트"/>
  
  <!-- 원본
  <div v-for="(list,i) in 원룸들" :key="i">
    <img :src="원룸들[i].image" class="room-img"> 
    <h4 @click="modal = true; 누른거 = i;">{{ list.title }}</h4>
    <p>{{ list.price }}원</p>
  </div> -->
  
  <!-- 컴포넌트 -->
  <!-- <Card :원룸들="원룸들" /> -->

  <Card @openModal="modal = true; 누른거 = $event"
  :원룸="원룸들[i]" v-for="(작명,i) in 원룸들" :key="작명"/>

  <!-- <Card :원룸="원룸들[i]" v-for="(작명,i) in 원룸들" :key="작명"/> -->

  <!-- 반복문 안쓰고 하드코딩
  <Card :원룸="원룸들[0]"/>  
  <Card :원룸="원룸들[1]"/>
  <Card :원룸="원룸들[2]"/>
  <Card :원룸="원룸들[3]"/>
  <Card :원룸="원룸들[4]"/>
  <Card :원룸="원룸들[5]"/>
   -->
</template>

<script>
import data from './assets/oneroom.js';
import {apple,apple2} from './assets/oneroom.js';
import Discount from './Discount.vue';
import Modal from './Modal.vue';
import Card from './Card.vue';
apple;
apple2;

export default {
  name: 'App',
  data(){
    return {
      오브젝트 : {name : 'kim', age : 20},
      누른거: 0,
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
    Discount : Discount,
    Modal,
    Card,
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
