<template>
  <ul class="SectionLinks">
    <li v-for="link in links" :key="link.href">
      <InternalLink :href="link.href">{{link.label}}</InternalLink>
    </li>
  </ul>
</template>

<script>
import InternalLink from '../atomic/links/InternalLink.vue';

export default {
  name: 'SectionLinks',
  components: {
    InternalLink,
  },
  props: {
    links: Array,
  },
}
</script>

<style>
  .SectionLinks {
    display: flex;
    flex-wrap: wrap;
    gap: 25px;
  }
</style>