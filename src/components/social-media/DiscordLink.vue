<template>
  <ExternalLink href="https://discord.com/invite/wotlk">
    <DiscordIcon width="38" />
  </ExternalLink>
</template>

<script>
import DiscordIcon from '../atomic/icons/DiscordIcon.vue';
import ExternalLink from '../atomic/links/ExternalLink.vue';

export default {
  name: 'DiscordLink',
  components: {
    DiscordIcon,
    ExternalLink,
  },
}
</script>

<style scoped>
  .DiscordLink {
    color: var(--text-primary);
  }
</style>