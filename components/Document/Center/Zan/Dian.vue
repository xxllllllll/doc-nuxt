
<template>
  <div class="like relative w-full h-auto grid justify-center">
      <div class="like_zan"
           :class="{active:isActive}"
            @click="show" >
      </div>
    </div>
  <p class="like_text text-sm text-gray-400 mb-4 mt-2 text-center">21人点赞</p>
  <div class="mt-5 w-auto flex justify-center">
    <ul class="touxiang flex justify-between w-5/12 ">
      <li v-for="items in Toux" @click="Toux1" :key="items.id" >
        <DocumentTanPop :obj="items"></DocumentTanPop>
      </li>
      <li>
        <img src="~assets/images/icon/shenglue.svg" class="border-2" alt="">
      </li>
    </ul>
  </div>
</template>

<script setup>
import {ref,reactive} from 'vue';
//点赞特效
let isActive = ref(false)
const show = ()=>{
  isActive.value = !isActive.value;
  console.log(isActive.value)
}



const Toux = ref([
  {id:1,url:'assets/images/icon/image.png'},
  {id:2,url:'assets/images/icon/image.png'},
  {id:3,url:'assets/images/icon/image.png'},
  {id:4,url:'assets/images/icon/image.png'},
  {id:5,url:'assets/images/icon/image.png'},
  {id:6,url:'assets/images/icon/image.png'},
  {id:7,url:'assets/images/icon/image.png'},
  {id:7,url:'assets/images/icon/image.png'},
])

// const D_zan = ()=>{
//   console.log($('.like_zan').className);
//
// }
</script>

<style scoped>
.active{
  -webkit-animation-name: like-module_like_ywZuk;
  animation-name: float;
  -webkit-animation-duration: .9s;
  animation-duration: .9s;
  -webkit-animation-iteration-count: 1;
  animation-iteration-count: 1;
  -webkit-animation-timing-function: steps(27);
  animation-timing-function: steps(27);
  -webkit-animation-fill-mode: forwards;
  animation-fill-mode: forwards;
}
.like_zan{
  display: inline-block;
  margin: -1px 0;
  width: 80px;
  height: 80px;
  background: url('assets/images/icon/zanback.png') no-repeat 0 0;
  background-size: auto 80px;

}
.touxiang>li>img{
  width:100%;
  height:100%;
  border-radius: 32px;
}
.touxiang>li{
  width:32px;
  height:32px;
}
@keyframes float{
  100% {
    background-position: -2160px 0;
    overflow: hidden;
  }
}

.hello>div{
  font-size:60px;
  animation: float 2s infinite alternate linear;
}

</style>