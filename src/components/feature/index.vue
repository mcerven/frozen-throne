<template>
  <li class="Feature">
    <div class="Feature__bg">
      <img class="Feature__bg-img" :src="imagePath" :alt="title">
    </div>
    <div class="Feature__content">
      <div class="Feature__title">
        <img class="Feature__icon" :src="iconPath" :alt="title + ' icon'" />
        <h3>{{title}}</h3>
      </div>
      <p class="Feature__description">
        {{description}}
      </p>
    </div>
  </li>
</template>

<script>
import { computed } from 'vue';

export default {
  props: {
    title: String,
    description: String,
    icon: String,
    image: String,
  },
  setup(props) {
    const iconPath = computed(() => {
      return require(`../../assets/images/features/icons/${props.icon}`);
    });

    const imagePath = computed(() => {
      return require(`../../assets/images/features/${props.image}`);
    });

    return {
      iconPath,
      imagePath,
    }
  }
}
</script>

<style>
  .Feature {
    position: relative;
    width: 280px;
    height: 450px;
    border-radius: 6px;
    background: black;
    overflow: hidden;
    --transition-duration: 250ms;
    --transition-function: ease-in-out;
  }

  .Feature__bg-img {
    min-width: 100%;
    min-height: 100%;
    object-fit: cover;
  }

  .Feature__bg::after {
    content: '';
    background: radial-gradient(
      150% 190px at center bottom,
      rgb(12, 109, 141),
      rgba(8, 77, 98, 0.8),
      rgba(7, 57, 76, 0.4));
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
  }

  .Feature:hover .Feature__bg::after {
    background: radial-gradient(
      150% 190px at center bottom,
      rgb(12, 109, 141),
      rgba(8, 77, 98, 0.8));
  }

  .Feature__content {
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    transition: all var(--transition-duration) var(--transition-function);
  }

  .Feature:hover .Feature__content {
    transform: translateY(-70%);
  }

  .Feature__icon {
    width: 40px;
  }

  .Feature__title, .Feature__description {
    position: absolute;
    padding: 0 1em;
    width: 100%;
    text-align: center;
  }

  .Feature__title {
    bottom: 30px;
    font-size: 1.6rem;
    padding: 0 1em;
  }

  .Feature__description {
    height: 100%;
    bottom: -100%;
    font-size: 1.2rem;
    line-height: 1.35;
    opacity: 0;
    transition: opacity var(--transition-duration) var(--transition-function);
  }

  .Feature:hover .Feature__description {
    opacity: 1;
  }
</style>