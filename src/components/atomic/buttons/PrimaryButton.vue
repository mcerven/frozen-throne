<template>
  <button v-bind="props" class="Button">
    <div class="Button__content">
      <slot></slot>
    </div>
  </button>
</template>

<script>
export default {
  name: 'Button',
  props: {
  },
}
</script>

<style scoped>
  .Button {
    font-size: 1rem;
    padding: 0.8em 1.5em;
    background: var(--bg-accent);
    border: none;
    border-radius: 2rem;
    color: var(--text-priamry);
    cursor: pointer;
    transition: transform 150ms ease;
  }
  .Button:hover {
    transform: scale(1.08);
  }
  .Button__content {
    display: flex;
    align-items: center;
    gap: 0.4em;
  }
</style>