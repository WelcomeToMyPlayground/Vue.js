<template>

  <!-- 이건 <div/> 6개를 컴포넌트화 한 것-->

  <!-- <div v-for="(list,i) in 원룸들" :key="i">
    <img :src="원룸들[i].image" class="room-img"> 
    <h4>{{ list.title }}</h4>
    <p>{{ list.price }}원</p>
  </div>
   -->
  
  <!-- <div> 1개를 컴포넌트화 -->
   <div>
    <img :src="원룸.image" class="room-img"> 
    <h4>{{ 원룸.title }}</h4>
    <p>{{ 원룸.price }}원</p>
  </div>
  
</template>

<script>
export default {
  name : 'Card',
  props: {
    // 원룸들 : Array,
    원룸 : Object,
  }
}
</script>

<style>

</style>