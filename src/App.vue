<script setup>
import Video1 from "@/assets/video/1.mp4"
import Video2 from "@/assets/video/2.mp4"
import Video3 from "@/assets/video/3.mp4"
import Video4 from "@/assets/video/4.mp4"
import Video5 from "@/assets/video/5.mp4"
import Video6 from "@/assets/video/6.mp4"
import Video7 from "@/assets/video/7.mp4"
import Video8 from "@/assets/video/8.mp4"
import Video9 from "@/assets/video/9.mp4"
import Video10 from "@/assets/video/10.mp4"
import TextImg from "@/assets/image/xy.gif"
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
        <li><video :src="Video1" autoplay loop muted :controls="false"></video></li>
        <li><video :src="Video2" autoplay loop muted :controls="false"></video></li>
        <li><video :src="Video3" autoplay loop muted :controls="false"></video></li>
        <li><video :src="Video4" autoplay loop muted :controls="false"></video></li>
        <li><video :src="Video5" autoplay loop muted :controls="false"></video></li>
        <li><video :src="Video6" autoplay loop muted :controls="false"></video></li>
      </ul>
      <!-- 大立方体 -->
      <ul class="cube bigCube">
        <li><video :src="Video7" autoplay loop muted :controls="false"></video></li>
        <li><video :src="Video8" autoplay loop muted :controls="false"></video></li>
        <li><video :src="Video9" autoplay loop muted :controls="false"></video></li>
        <li><video :src="Video10" autoplay loop muted :controls="false"></video></li>
        <li><video :src="Video10" autoplay loop muted :controls="false"></video></li>
        <li><video :src="Video10" autoplay loop muted :controls="false"></video></li>
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

.cube li video {
  width: 100%;
  height: 100%;
}

.cube li:nth-child(1) {
  transform: rotateX(0deg) translateZ(50px);
}

.cube li:nth-child(2) {
  transform: rotateX(180deg) rotateZ(180deg) translateZ(50px);
}

.cube li:nth-child(3) {
  transform: rotateX(-90deg) translateZ(50px);
}

.cube li:nth-child(4) {
  transform: rotateX(90deg) translateZ(50px);
}

.cube li:nth-child(5) {
  transform: rotateY(-90deg) translateZ(50px);
}

.cube li:nth-child(6) {
  transform: rotateY(90deg) translateZ(50px);
}

.bigCube {
  width: 200px;
  height: 200px;
  margin: -100px 0 0 -100px;
}

.bigCube li:nth-child(1) {
  transform: rotateX(0deg) translateZ(100px);
}

.bigCube li:nth-child(2) {
  transform: rotateX(180deg) rotateZ(180deg) translateZ(100px);
}

.bigCube li:nth-child(3) {
  transform: rotateX(-90deg) translateZ(100px);
}

.bigCube li:nth-child(4) {
  transform: rotateX(90deg) translateZ(100px);
}

.bigCube li:nth-child(5) {
  transform: rotateY(-90deg) translateZ(100px);
}

.bigCube li:nth-child(6) {
  transform: rotateY(90deg) translateZ(100px);
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
