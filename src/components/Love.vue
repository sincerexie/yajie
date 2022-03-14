<script setup lang="ts">
  import { ref, onMounted } from 'vue'
  const devicesRef = ref<HTMLInputElement | null>(null);
  const congratsRef = ref<HTMLInputElement | null>(null)
  onMounted(() => {
    const screen = window.screen.width;
    const scaleValue = `scale(${screen / 1080})`
    if (devicesRef.value) {
      devicesRef.value.style.transform = scaleValue;
    }
    if (congratsRef.value) {
      congratsRef.value.style.transform = scaleValue;
    }
  });
</script>

<template>
  <main class="devices" ref="devicesRef">
    <h1><span class="iu">I</span> <span class="love">Love</span> <span class="heart">❤</span> <span class="yo">Yo</span><span class="iu">u</span></h1>
  </main>
  <div class="congrats" ref="congratsRef">
    <span></span>
    <span></span>
    <span></span>
    <span></span>
    <span></span>
  </div>
  <div class="name">
    雅洁小宝贝~
  </div>
</template>

<style scoped>
.name {
  position: absolute;
  font-size: 0.25rem;
  color: #fff;
  left: 50%;
  top: 1rem;
  font-weight: bold;
  transform: translate(-50%, -50%);
}
.devices {
 width: 1080px;
 box-shadow: 0px 0px 0px 10px #fff;
 border-radius: 20px;
 height: 580px;
 display: flex;
 align-items: center;
 justify-content: center;
 position: relative;
 transform: scale(calc(100vw/1080));
 animation: devices var(--cubezier);
}
.devices:after {
 content:"";
 position: absolute;
 background-color: #fff;
 width: 15px;
 height: 15px;
 border-radius: 50%;
 bottom: 20px;
}
.devices:before {
 content: "";
  width: 100%;
 background-color: rgba(0,0,0,0.1);
 border-radius: 100%;
 height: 30px;
 position: absolute;
 bottom: -80px;
 z-index: -1;
}


h1 {
 color: var(--purple);
 text-transform: uppercase;
 text-align: center;
 animation: fontSize var(--cubezier);
}
h1 span {
 overflow: hidden;
 position: relative;
 display: inline-block;
 text-align: center;
}
.heart {
 color: var(--red);
 animation: heart var(--cubezier),   heartbeat 1s ease-in-out infinite, heartWhite ease-out 6s infinite;
}

.love {
  animation: love var(--cubezier);
}
.yo {
  animation: yo var(--cubezier);
}
.iu {
  animation: iu var(--cubezier);
}
.congrats {
  width: 320px; 
 height: 680px;
 position: absolute;
 display: flex;
 align-items: center;
 justify-content: center;
 
 
}
.congrats span {
 content: "";
 width: 0;
 height: 0;
 position: absolute;
 border: 4px solid var(--red);
 border-radius: 50%;
 animation: congrats ease-out 6s infinite;
}
.congrats span:nth-child(1){
 top: 270px;
 left: 60px;
}
.congrats span:nth-child(2){
 top: 230px;
 left: 50%;
}
.congrats span:nth-child(3){
 top: 270px;
 right: 60px;
}
.congrats span:nth-child(4){
 bottom: 270px;
 right: 60px;
}
.congrats span:nth-child(5){
 bottom: 270px;
 left: 80px;
}


/* ANIMATIONS */

@keyframes devices {
 0% { width: 990px; height: 580px;}
 25% { width: 720px; height: 580px;}
 50% { width: 480px; height: 580px;}
 72% { width: 320px; height: 680px;}
 100% { width: 990px; height: 580px;}
}

@keyframes fontSize {
 0% { 
   font-size: 90px;
   letter-spacing: 18px;
 }
 25% { 
   font-size: 90px;
   letter-spacing: 10px;
 }
 50% { 
   font-size: 90px;
   letter-spacing: 5px;
 }
 75% { 
   font-size: 150px;
   letter-spacing: 0;
 }
 100% { 
   font-size: 90px;
   letter-spacing: 18px;
 } 

}

@keyframes love {
 0% { width: auto;}
 25% { width: 0;}
 50% {  width: 0;}
 75% {  width: 0;}
 100% { width: auto;}
}


@keyframes yo {
 0% { width: auto;}
 25% { width: auto;}
 50% {  width: 0;}
 75% {  width: 0;}
 100% { width: auto;}
}

@keyframes iu {
 0% { width: auto;}
 25% { width: auto;}
 50% {  width: auto;}
 75% {  width: 0;}
 100% { width: auto;}
}

@keyframes heart {
 0% { width: 0;}
 25% { width: auto;}
 50% {  width: auto;}
 75% {  width: auto;}
 100% { width: 0;}
} 

@keyframes heartbeat {
 0% {transform: scale(1);}
 50% {transform: scale(1.5);}
 100% {transform: scale(1);}
}


@keyframes congrats {
 0% {
  width: 0;
  height: 0;
  opacity: 0;
 }
 58% {
    width: 0;
  height: 0;
  opacity: 0;
 }
 60% {
  width: 30px;
  height: 30px;
  opacity: 1;
 }
 80% {
   width: 100px;
  height: 100px;
  opacity: 0;
 }
  81% {
   width: 0;
  height: 0;
  opacity: 0;
 }
 100% {
   width: 0;
  height: 0;
  opacity: 0;
 }
}

@keyframes bgRed {
 0% { background-color: var(--yellow);}
 58% { background-color: var(--yellow);}
 60% { background-color: var(--red);}
 80% { background-color: var(--red);}
  81% { background-color: var(--yellow);}
}

@keyframes heartWhite {
 0% { color: var(--red);}
 58% { color: var(--red);}
 60% { color: #fff;}
 80% { color: #fff;}
  81% { color: var(--red);}
}

/* RESPONSIVE */
@media all and (max-width: 1080px) and (min-width: 720px) {
 .devices {
  width:720px;
 }
}
@media all and (max-width: 1080px) and (min-width: 720px) {
 .devices {
  width:720px;
 }
}
</style>
