<script setup>
import { ref } from 'vue';



let qty = ref (2)

function addValue(){
  qty.value++
  console.log(qty)
}

function minValue() {
  if(qty.value > 0){
    qty.value--
  }
}
  


</script>

<template>
 <div class="wrapper">
  <div class="profile">
    <div class="ballon" v-show="qty">{{qty}}</div>
  </div>
  <div class="button-wrapper">
    <div class="button" @click="minValue">-</div>
    <div class="button" @click="addValue">+</div>

  </div>
  <div v-if ="qty>0">ME ESCRIBIERON 😊</div>
  <div v-if="qty<=0">NADIE ME ESCRIBE 😢</div>
 </div>
</template>

<style scoped>

.profile{
background-image: url('https://profilemagazine.com/wp-content/uploads/2020/04/Ajmere-Dale-Square-thumbnail.jpg');
background-size: cover;
background-color: rgb(184, 89, 168);
width: 160px;
height: 160px;
margin: 0 auto;
border-radius: 100%;
position: relative;
}
.wrapper{
  overflow: hidden;
  background-color: #1B7F79;
  width: 60%;
  border-radius: 12px;
  margin: 0 auto;
  padding-top: 18px;
  
}
.button-wrapper{
  text-align: center;
  margin-top: 16px;
  margin-bottom: 16px;
}

.button{
  background-color: beige;
  display: inline-block;
  padding: 4px 0px;
  border-radius: 4px;
  width: 32px;
  margin: 0 8px;

}
.button:hover{
  cursor: pointer;
  background-color:#FF4858;
}
.ballon{
  width: 32px;
  height: 32px;
  background-color: #FF4858;
  border-radius: 100%;
  display:flex;
  justify-content: center;
  align-items: center;
  color: white;
  position: absolute;
  top: 0;
  right: 0;
  
}
</style>
