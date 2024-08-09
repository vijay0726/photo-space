<script setup>
// import Video1 from "@/assets/video/1.mp4"
// import Video2 from "@/assets/video/2.mp4"
// import Video3 from "@/assets/video/3.mp4"
// import Video4 from "@/assets/video/4.mp4"
// import Video5 from "@/assets/video/5.mp4"
import Video6 from "@/assets/video/6.mp4"
// import Video7 from "@/assets/video/7.mp4"
// import Video8 from "@/assets/video/8.mp4"
// import Video9 from "@/assets/video/9.mp4"
// import Video10 from "@/assets/video/10.mp4"
import TextImg from "@/assets/image/xy.gif"
import img1 from "@/assets/image/1.jpg"
import img2 from "@/assets/image/2.jpg"
import img3 from "@/assets/image/3.jpg"
import img4 from "@/assets/image/4.jpg"
import img5 from "@/assets/image/5.jpg"
import img6 from "@/assets/image/6.jpg"
import img7 from "@/assets/image/7.jpg"
import img8 from "@/assets/image/8.jpg"
import img9 from "@/assets/image/9.jpg"
import img10 from "@/assets/image/10.jpg"
import img11 from "@/assets/image/11.jpg"
import img12 from "@/assets/image/12.jpg"


import { ref } from "vue"

const bgVideoRef = ref()
const playBgVideo = () => {
  bgVideoRef.value.play()
}
</script>

<template>
  <div class="main" @click="playBgVideo">
    <!-- 背景 -->
    <video ref="bgVideoRef" :src="Video6" autoplay loop class="bg" :controls="false"></video>
    <img class="xy" :src="TextImg" alt="心雨一定会稳稳地幸福呀！">
    <div class="cubeBox">
      <!-- 小立方体 -->
      <ul class="cube">
        <li><img :src="img1" /></li>
        <li><img :src="img2" /></li>
        <li><img :src="img3" /></li>
        <li><img :src="img4" /></li>
        <li><img :src="img5" /></li>
        <li><img :src="img6" /></li>
      </ul>
      <!-- 大立方体 -->
      <ul class="cube bigCube">
        <li><img :src="img7" /></li>
        <li><img :src="img8" /></li>
        <li><img :src="img9" /></li>
        <li><img :src="img10" /></li>
        <li><img :src="img11" /></li>
        <li><img :src="img12" /></li>
      </ul>
    </div>
  </div>
</template>

<style scoped>
.main {
  width: 100%;
  height: 100vh;
  perspective: 800;
  background: #000;
}


.cubeBox {
  width: 200px;
  height: 200px;
  position: absolute;
  top: 50%;
  left: 50%;
  margin: -100px 0 0 -100px;
  transform-style: preserve-3d;
}

.bg {
  width: 100%;
  height: 100%;
}

.xy {
  position: fixed;
  top: 10px;
  left: 0px;
  z-index: 1;
  width: 100%;
}

.cube {
  width: 100px;
  height: 100px;
  position: absolute;
  top: 50%;
  left: 50%;
  margin: -50px 0 0 -50px;
  transform-style: preserve-3d;
  transform: rotateX(-10deg) rotateY(45deg);
  animation: move 4s linear infinite;
}

.cube li {
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0;
  left: 0;
  transition: all 1s ease;
}

.cube li img {
  width: 100%;
  height: 100%;
}

.cube li:nth-child(1) {
  transform: rotateX(0deg) translateZ(70px);
}

.cube li:nth-child(2) {
  transform: rotateX(180deg) rotateZ(180deg) translateZ(70px);
}

.cube li:nth-child(3) {
  transform: rotateX(-90deg) translateZ(70px);
}

.cube li:nth-child(4) {
  transform: rotateX(90deg) translateZ(70px);
}

.cube li:nth-child(5) {
  transform: rotateY(-90deg) translateZ(70px);
}

.cube li:nth-child(6) {
  transform: rotateY(90deg) translateZ(70px);
}

.bigCube {
  width: 200px;
  height: 200px;
  margin: -100px 0 0 -100px;
}

.bigCube li:nth-child(1) {
  transform: rotateX(0deg) translateZ(120px);
}

.bigCube li:nth-child(2) {
  transform: rotateX(180deg) rotateZ(180deg) translateZ(120px);
}

.bigCube li:nth-child(3) {
  transform: rotateX(-90deg) translateZ(120px);
}

.bigCube li:nth-child(4) {
  transform: rotateX(90deg) translateZ(120px);
}

.bigCube li:nth-child(5) {
  transform: rotateY(-90deg) translateZ(120px);
}

.bigCube li:nth-child(6) {
  transform: rotateY(90deg) translateZ(120px);
}

@keyframes move {
  0% {
    transform: rotateX(-13deg) rotateY(0deg);
  }

  100% {
    transform: rotateX(-13deg) rotateY(360deg);
  }
}

.cubeBox:hover .bigCube li:nth-child(1) {
  transform: rotateX(0deg) translateZ(200px);
}

.cubeBox:hover .bigCube li:nth-child(2) {
  transform: rotateX(180deg) rotateZ(180deg) translateZ(200px);
}

.cubeBox:hover .bigCube li:nth-child(3) {
  transform: rotateX(-90deg) translateZ(200px);
}

.cubeBox:hover .bigCube li:nth-child(4) {
  transform: rotateX(90deg) translateZ(200px);
}

.cubeBox:hover .bigCube li:nth-child(5) {
  transform: rotateY(-90deg) translateZ(200px);
}

.cubeBox:hover .bigCube li:nth-child(6) {
  transform: rotateY(90deg) translateZ(200px);
}
</style>
