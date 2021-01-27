<template>
  <ExternalLink href="https://github.com/mcerven">
    <GithubIcon width="30" />
  </ExternalLink>
</template>

<script>
import GithubIcon from '../atomic/icons/GithubIcon.vue';
import ExternalLink from '../atomic/links/ExternalLink.vue';

export default {
  name: 'GithubLink',
  components: { 
    GithubIcon,
    ExternalLink,
  },
}
</script>

<style scoped>
  .GithubIcon {
    color: var(--text-primary);
  }
</style>