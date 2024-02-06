<template>

  <div class="menu">
    <a v-for="list in menu" :key="list">{{list}}</a>

  </div>

  <h1>원룸샵</h1>
  <div>
    <img src="./assets/room0.jpg" class="room-img">
    <h4 :style="스타일">{{ products[0] }}</h4>
    <p>{{price1}}만원</p>
    <button v-on:click="increase1">허위매물신고</button>
    <span>신고수 : {{ 신고수[0] }} </span>
  </div>

  <div>
    <img src="./assets/room1.jpg" class="room-img">
    <h4 :style="스타일1[1]">{{ products[1] }}</h4>
    <p>{{prices[1]}}만원</p>
    <button @click="increase2">허위매물신고</button>
    <span>신고수 : {{ 신고수[1] }} </span>
  </div>

  <div>
    <img src="./assets/room2.jpg" class="room-img">
    <h4 style="color:red">{{ products[2] }}</h4>
    <p>{{prices[2]}}만원</p>
    <button v-on:click="increase3()">허위매물신고</button> 
    <span>신고수 : {{ 신고수[2] }}</span>
  </div>
  
  <!-- 축약 -->
  <!-- <div v-for="productList in products" :key="productList">
    <h4>{{ productList }}</h4>
    <p>{{ price1 }}</p>
  </div> -->

</template>

<script>

function 어쩌구(){
  console.log('어쩌구우우');
}

어쩌구();

export default {
  name: 'App',
  data(){
    return {
      price1 : 60,
      price2 : 70,
      prices : [60,70,80],
      스타일 : 'color:red',
      스타일1 : ['color:red','color:blue','color:yellow'],
      products : ['역삼동원룸','천호동원룸','마포구원룸'],
      menu : ['Home','Shop','About'],
      신고수 : [0,0,0]
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
</style>
