<template>
  <section id="timeline">
    <header>
      <span class="section-name">Raids Timeline</span>
      <h2>Conquer the Frozen North</h2>
    </header>
    <div>
      <div class="swiper-container">
        <ul class="swiper-wrapper timeline">
          <li class="swiper-slide" v-for="item in events" :key="item.title">
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
    </div>
  </section>
</template>

<script>
import Swiper from 'swiper';

export default {
  name: 'Timeline',
  props: {
    events: Array,
  },
  setup() {
    const getImagePath = image => {
      return require(`../../assets/images/timeline/${image}`)
    };

    return {
      getImagePath,
    }
  },
  mounted() {
    new Swiper('.swiper-container', {
      slidesPerView: 3,
      grabCursor: true,
    });    
  }
}
</script>

<style scoped>
  .swiper-container {
    width: 100%;
    height: 100%;
    margin: 50px 0;
    overflow: hidden;
    padding: 0 20px 30px 20px;
  }
  
  .swiper-slide {
    width: 200px;
    text-align: center;
    font-size: 18px;
  }

  .timeline {
    margin: 50px 0;
    list-style-type: none;
    display: flex;
    padding: 0;
    text-align: center;
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