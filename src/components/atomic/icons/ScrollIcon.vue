<template>
  <svg class="scroll-icon" version="1.1" id="Layer_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" width="80px" height="80px" viewBox="-285 377 40 40" xml:space="preserve">
    <g id="mouse-wheel">
      <path fill="currentColor" d="M-265,388.1c-0.9,0-1.6,0.7-1.6,1.6v4.1c0,0.9,0.7,1.6,1.6,1.6s1.6-0.7,1.6-1.6v-4.1
        C-263.4,388.8-264.1,388.1-265,388.1" />
    </g>
    <g id="mouse-body">
      <path fill="currentColor" d="M-264,378.2h-1.9c-6.2,0.5-10.9,5.5-10.9,11.6v14.3c0,6.5,5.3,11.7,11.8,11.7
        s11.8-5.3,11.8-11.7v-14.3C-253.1,383.7-257.9,378.7-264,378.2z M-255.1,404.2c0,5.4-4.4,9.8-9.9,9.8c-5.4,0-9.9-4.4-9.9-9.8
        v-14.4c0-5.4,4.5-9.8,9.9-9.8s9.9,4.4,9.9,9.8V404.2z" />
    </g>
  </svg>
</template>
<style scoped>
  #mouse-wheel {
    animation: moveDown 3s 0s linear infinite;
  }

  @keyframes moveDown {
    0% {
      transform: translateY(0);
      opacity: 0;
    }
    18% {
      opacity: 0;
    }
    20% {
      opacity: 1;
    }
    80% {
      transform: translateY(0);
      opacity: 1;
    }
    85% {
      transform: translateY(10px);
      opacity: 1;
    }
    100% {
      transform: translateY(10px);
      opacity: 0;
    }
  }
</style>