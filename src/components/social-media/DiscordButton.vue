<template>
  <PrimaryButton @click="handleClick" style="color: var(--text-primary);">
    <DiscordIcon width="28" />
    <span>Join Discord</span>
  </PrimaryButton>
</template>

<script>
import PrimaryButton from '../atomic/buttons/PrimaryButton.vue';
import DiscordIcon from '../atomic/icons/DiscordIcon.vue';

export default {
  components: { 
    PrimaryButton,
    DiscordIcon,
  },
  name: 'DiscordButton',
  methods: {
    handleClick() {
      window.open('https://discord.com/invite/wotlk', '_blank');
    }
  }
}
</script>
