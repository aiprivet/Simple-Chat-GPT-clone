<template>
  <div class="stage">
    <div class="layer"></div>
    <div class="layer"></div>
    <div class="layer"></div>
    <div class="layer"></div>
    <div class="layer"></div>
    <div class="layer"></div>
    <div class="layer"></div>
    <div class="layer"></div>
    <div class="layer"></div>
    <div class="layer"></div>
    <div class="layer"></div>
    <div class="layer"></div>
  </div>
</template>

<script setup></script>

<style>
@import url("//fonts.googleapis.com/css?family=Pacifico&text=Chat GPT");

* *,
*::before,
*::after {
  animation-play-state: running !important;
}

.stage {
  height: 400px;
  width: 100px;
  margin: auto;
  position: absolute;
  z-index: 0;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  perspective: none;
}

.layer {
  position: absolute;
  animation: ಠ_ಠ 5s infinite alternate ease-in-out -7.5s;
  animation-fill-mode: forwards;
  transform: rotateY(15deg) rotateX(18deg) translateZ(0);
}

.layer:after {
  font: 120px/0.65 "Pacifico", "Kaushan Script", Futura, "Roboto",
    "Trebuchet MS", Helvetica, sans-serif;
  content: "Chat\aGPT🚀";
  white-space: pre;
  text-align: center;
  position: absolute;
  top: 50px;
  color: whitesmoke;
  letter-spacing: -2px;
  text-shadow: 4px 0 10px rgba(0, 0, 0, 0.13);
}

.layer:nth-child(1):after {
  transform: translateZ(0px);
}

.layer:nth-child(2):after {
  transform: translateZ(-1.5px);
}

.layer:nth-child(3):after {
  transform: translateZ(-3px);
}

.layer:nth-child(4):after {
  transform: translateZ(-4.5px);
}

.layer:nth-child(5):after {
  transform: translateZ(-6px);
}

.layer:nth-child(6):after {
  transform: translateZ(-7.5px);
}

.layer:nth-child(7):after {
  transform: translateZ(-9px);
}

.layer:nth-child(8):after {
  transform: translateZ(-10.5px);
}

.layer:nth-child(9):after {
  transform: translateZ(-12px);
}

.layer:nth-child(10):after {
  transform: translateZ(-13.5px);
}

.layer:nth-child(11):after {
  transform: translateZ(-15px);
}

.layer:nth-child(12):after {
  transform: translateZ(-16.5px);
}

.layer:nth-child(13):after {
  transform: translateZ(-18px);
}

.layer:nth-child(14):after {
  transform: translateZ(-19.5px);
}

.layer:nth-child(15):after {
  transform: translateZ(-21px);
}

.layer:nth-child(16):after {
  transform: translateZ(-22.5px);
}

.layer:nth-child(17):after {
  transform: translateZ(-24px);
}

.layer:nth-child(18):after {
  transform: translateZ(-25.5px);
}

.layer:nth-child(19):after {
  transform: translateZ(-27px);
}

.layer:nth-child(20):after {
  transform: translateZ(-28.5px);
}

.layer:nth-child(n + 10):after {
  -webkit-text-stroke: 3px rgba(0, 0, 0, 0.25);
}

.layer:nth-child(n + 11):after {
  -webkit-text-stroke: 15px rgb(176, 30, 255);
  text-shadow: 6px 0 6px #4d006b, 5px 5px 5px #320051, 0 6px 6px #6b0068;
}

.layer:nth-child(n + 12):after {
  -webkit-text-stroke: 15px #8c00ea;
}

.layer:last-child:after {
  -webkit-text-stroke: 17px rgba(0, 0, 0, 0.1);
}

.layer:first-child:after {
  color: #fff;
  text-shadow: none;
}

@keyframes ಠ_ಠ {
  100% {
    transform: rotateY(-15deg) rotateX(-18deg);
  }
}
@media screen and (max-width: 1200px) {
  .stage {
    height: 100px;
    width: 300px;
  }
  .layer:after {
  font: 90px/0.65 "Pacifico", "Kaushan Script", Futura, "Roboto",
    "Trebuchet MS", Helvetica, sans-serif;
  }
}
</style>
