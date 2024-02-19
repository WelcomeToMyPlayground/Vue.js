<template>

  <div class="black-bg" v-if="modal == true">
    <div class="white-bg">
      <Discount/>
      <img :src="원룸들[누른거].image" style="width:100%">
      <h4>{{ 원룸들[누른거].title}}</h4>
      <p>상품 설명 : {{ 원룸들[누른거].content}}</p>
      <p>가격 : {{ 원룸들[누른거].price }}원</p>
      <button @onclick="$emit('closeModal')">닫기</button>
      <!-- <button v-on:click="modal = false">닫기</button> -->
    </div>
  </div>

</template>

<script>
export default {
  name : 'Modal',
  props: {
    원룸들 : Array,
    누른거 : Number,
    modal : Boolean,
  }
}
</script>

<style>

</style>