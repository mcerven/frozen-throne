<template>
  <a class="Link" :href="href">
    <slot></slot>
  </a>
</template>

<script>

export default {
  props: {
    href: String,
  }
}
</script>
