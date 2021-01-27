<template>
  <section id="features">
    <header>
      <span class="section-name">Features</span>
      <h2>Frozen Throne Awaits</h2>
    </header>
    <div class="row">
      <ul class="Features__list">
        <Feature v-for="feature in features" v-bind="feature" :key="feature.title" />
      </ul>
    </div>
  </section>
</template>

<script>
import Feature from '../feature';

export default {
  name: 'Features',
  components: {
    Feature,
  },
  props: {
    features: Array,
  }
}
</script>

<style>
  .Features__list {
    width: 100%;
    margin: 0 auto;
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 2em 1.2em;
  }
</style>