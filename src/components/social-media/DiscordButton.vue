<template>
  <PrimaryButton @click="handleClick" style="color: var(--text-primary);" role="link">
    <DiscordIcon width="28" />
    <span>Join Discord</span>
  </PrimaryButton>
</template>

<script>
import PrimaryButton from '../atomic/buttons/PrimaryButton.vue';
import DiscordIcon from '../atomic/icons/DiscordIcon.vue';

export default {
  name: 'DiscordButton',
  components: { 
    PrimaryButton,
    DiscordIcon,
  },
  methods: {
    handleClick() {
      window.open('https://discord.com/invite/wotlk', '_blank');
    }
  }
}
</script>
