<template>
  <main>
    <Home title="All must serve the one, true King" subtitle="Coming soon" />
    <Introduction />
    <Deathknight />
  </main>
</template>

<script>
import './global-styles.css';
import Home from './components/sections/Home.vue';
import Introduction from './components/sections/Introduction.vue';
import Deathknight from './components/sections/Deathknight.vue';

export default {
  name: 'App',
  components: {
    Home,
    Introduction,
    Deathknight,
  }
}
</script>
,
    Deathknight