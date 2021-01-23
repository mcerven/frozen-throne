<template>
  <Button @click="handleClick" style="color: var(--text-primary);">
    <img width="24" src="../../assets/images/discord.svg" alt="Frozen Throne" />
    <span>Join Discord</span>
  </Button>
</template>

<script>
import Button from '../button'

export default {
  components: { Button },
  name: 'DiscordButton',
  methods: {
    handleClick() {
      window.open('https://discord.com/invite/wotlk', '_blank');
    }
  }
}
</script>
