<template>
  <div v-for="(list,i) in 원룸들" :key="i">
    <img :src="원룸들[i].image" class="room-img"> 
    <h4>{{ list.title }}</h4>
    <p>{{ list.price }}원</p>
  </div>
</template>

<script>
export default {
  name : 'Card',
  props: {
    원룸들 : Array,
  }
}
</script>

<style>

</style>