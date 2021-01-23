<template>
  <div class="Talent">
    <img class="Talent__img" :src="imagePath" :alt="name">
    <span class="Talent__name">{{name}}</span>
    <span class="Talent__role">{{role}}</span>
  </div>
</template>

<script>
export default {
  props: {
    name: String,
    role: String,
    image: String,
  },
  computed: {
    imagePath() {
      return require(`../../../assets/images/deathknight/talents/${this.image}`);
    }
  }
}
</script>

<style>
  .Talent {
    padding: 0.8em 1.6em;
    border: 1px solid var(--bg-accent);
    display: flex;
    align-items: center;
    gap: 1em;
  }

  .Talent__img {
    width: 50px;
    object-fit: contain;
    border-radius: 50%;
    border: 5px solid var(--bg-accent);
  }

  .Talent__name, .Talent__role {
    font-size: 1.4rem;
  }

  .Talent__role {
    color: var(--text-primary);
    opacity: 0.6;
  }
</style>