<template>

  <div class="black-bg" v-if="modal == true">
    <div class="white-bg">
      <Discount/>
      <img :src="원룸들[누른거].image" style="width:100%">
      <h4>{{ 원룸들[누른거].title}}</h4>
      <p>상품 설명 : {{ 원룸들[누른거].content}}</p>
      <!-- <input v-model.number ="month"> -->
      <input @input="month = $event.target.value">
      <p>{{ month }}개월 선택함 : {{ 원룸들[누른거].price * month }}원</p>
      <button @click="$emit('closeModal')">닫기</button>
      <!-- <button v-on:click="modal = false">닫기</button> -->
    </div>
  </div>

</template>

<script>
export default {
  name : 'Modal',
  data(){
    return{
      month : 1
    }
  },
  watch : {
    month(a){
      if(isNaN(a) == true){
        alert('문자는 입력할 수 없습니다')
        this.month = 1;
      } else if(a == ' '){
        alert('공백은 입력하실 수 없습니다')
        this.month = 1;
      }
      // month라는 데이터가 변할 때마다 여기있는 코드가 실행됨 
    }
  },
  props: {
    원룸들 : Array,
    누른거 : Number,
    modal : Boolean,
  }
}
</script>

<style>

</style>