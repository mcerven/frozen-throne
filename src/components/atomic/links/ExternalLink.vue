<template>
  <a class="Link" :href="href" target="_blank" rel="noreferrer noopener">
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
