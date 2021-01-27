<template>
  <a class="Link" :href="href">
    <slot></slot>
  </a>
</template>

<script>

export default {
  name: 'InternalLink',
  props: {
    href: String,
  }
}
</script>
