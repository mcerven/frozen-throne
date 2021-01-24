<template>
  <div class="Talent">
    <img class="Talent__img" :src="imagePath" :alt="name">
    <span class="Talent__name">{{name}}</span>
    <span class="Talent__role">{{role}}</span>
  </div>
</template>

<script>
import { computed } from 'vue';

export default {
  props: {
    name: String,
    role: String,
    image: String,
  },
  setup(props) {
    const imagePath = computed(() => {
      return require(`../../../assets/images/deathknight/talents/${props.image}`)
    });

    return {
      imagePath,
    }
  }
}
</script>

<style>
  .Talent {
    padding: 0.8em 1.6em;
    border: 1px solid transparent;
    display: flex;
    align-items: center;
    gap: 1em;
    transition: border-color 0.3s ease;
  }

  .Talent:hover {
    border-color: var(--bg-accent);
  }

  .Talent__img {
    width: 50px;
    object-fit: contain;
    border-radius: 50%;
    border: 5px solid var(--bg-accent);
  }

  .Talent__name, .Talent__role {
    font-size: 1.25rem;
  }

  .Talent__role {
    color: var(--text-primary);
    opacity: 0.6;
  }
</style>