<template>
  <main class="scroll-container">
    <Home title="All must serve the one, true King" subtitle="Coming soon" />
    <Introduction />
    <Deathknight />
    <Timeline :events="timelineEvents" />
    <Features />
  </main>
</template>

<script>
import './global-styles.css';
import Home from './components/sections/Home.vue';
import Introduction from './components/sections/Introduction.vue';
import Deathknight from './components/sections/Deathknight.vue';
import Timeline from './components/sections/Timeline.vue';
import Features from './components/sections/Features.vue';

export default {
  name: 'App',
  components: {
    Home,
    Introduction,
    Deathknight,
    Timeline,
    Features,
  },
  setup() {
    const timelineEvents = [
      { title: 'Launch', dateLabel: '2021', image: 'wow3.0.png', },
      { title: 'Secrets of Ulduar', dateLabel: 'TO BE ANNOUNCED', image: 'wow3.1.png', },
      { title: 'Call of the Crusade', dateLabel: 'TO BE ANNOUNCED', image: 'wow3.2.png', },
      { title: 'Fall of the Lich King', dateLabel: 'TO BE ANNOUNCED', image: 'wow3.3.png', },
    ];

    return {
      timelineEvents,
    }
  }
}
</script>
