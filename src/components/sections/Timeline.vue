<template>
  <section id="timeline">
    <header>
      <span class="section-name">{{sectionName}}</span>
      <h2>{{title}}</h2>
    </header>
    <div class="timeline__bg">
    </div>
    <div class="row">
      <ul class="swiper-container scrollbar-hidden"
        ref="swiper"
        @mousedown="swipeStart"
        @mouseup="swipeStop"
        @mouseleave="swipeStop"
        @mousemove="swipeMove"
        >
        <li class="swiper-item" v-for="item in events" :key="item.title">
          <div class="timeline-item__top">
            <img class="timeline-item__image" :src="getImagePath(item.image)" :alt="item.title">
          </div>
          <div class="timeline-item__bottom">
            <h3 class="title-label">{{item.title}}</h3>
            <p class="date-label">{{item.dateLabel}}</p>
          </div>
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
import { ref } from 'vue';

export default {
  name: 'Timeline',
  props: {
    sectionName: String,
    title: String,
    events: Array,
  },
  setup() {
    const getImagePath = image => require(`../../assets/images/timeline/${image}`);
    const swiper = ref(null);

    let isSwiping = false;
    let startX = null;
    let scrollLeft = null;

    function swipeStart(e) {
      console.log(swiper.value)
      isSwiping = true;
      startX = e.pageX - swiper.value.offsetLeft;
      scrollLeft = swiper.value.scrollLeft;
      swiper.value.classList.add('active');
    }
    function swipeStop() {
      isSwiping = false;
      swiper.value.classList.remove('active');
    }
    function swipeMove(e) {
      if(!isSwiping) return;
      
      e.preventDefault();
      
      const x = e.pageX - swiper.value.offsetLeft;
      const swipeSpeed = 1;
      const step = (x - startX) * swipeSpeed;
      
      swiper.value.scrollLeft = scrollLeft - step;
    }

    return {
      getImagePath,
      swiper,
      swipeStart,
      swipeStop,
      swipeMove,
    }
  },
  mounted() {
    
  }
}
</script>

<style scoped>
  .timeline__bg {
    background:
      linear-gradient(to bottom, var(--bg-primary), rgba(0, 0, 0, 0.68) 30%, rgba(0, 0, 0, 0.85)),
      url('../../assets/images/background/howling-fjord.jpg');
    background-position: center center;
    background-repeat: no-repeat;
    background-size: cover;
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
  }

  .swiper-container {
    position: relative;
    width: 100%;
    overflow-x: scroll;
    overflow-y: hidden;
    white-space: nowrap;
    will-change: transform;
    user-select: none;
    cursor: pointer;
  }

  .scrollbar-hidden {
      -ms-overflow-style: none;  /* Internet Explorer 10+ */
      scrollbar-width: none;  /* Firefox */
  }
  .scrollbar-hidden::-webkit-scrollbar { 
      display: none;  /* Safari and Chrome */
  }

  .swiper-container.active {
    cursor: grabbing;
  }
  
  .swiper-item {
    display: inline-block;
    height: 300px;
    width: 300px;
  }

  .timeline-item__top, .timeline-item__bottom {
    padding: 20px 15px;
  }

  .timeline-item__top {
    width: 100%;
    margin-bottom: 20px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    font-weight: 100;
    height: 110px;
  }

  .timeline-item__bottom {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    border-top: 4px solid var(--bg-accent);
    position: relative;
    gap: 0.6em;
  }

  .timeline-item__bottom:before {
    --timeline-point-width: 25px;
    content: '';
    width: var(--timeline-point-width);
    height: var(--timeline-point-width);
    background-color: #ffffff;
    border-radius: var(--timeline-point-width);
    border: 4px solid var(--bg-accent);
    position: absolute;
    top: -15px;
    left: 50%;
    transform: translateX(-50%);
  }

  .timeline-item__image {
    height: 100%;
  }
  
  .title-label {
    font-weight: 600;
  }

  .date-label {
    opacity: 0.8;
  }
</style>