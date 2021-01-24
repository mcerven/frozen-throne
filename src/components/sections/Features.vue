<template>
  <section id="Features">
    <header>
      <span class="section-name">Features</span>
      <h2>Frozen Throne Awaits</h2>
    </header>
    <div class="row">
      <ul class="Features__list">
        <Feature v-for="feature in features" v-bind="feature" :key="feature.title" />
      </ul>
    </div>
  </section>
</template>

<script>
import Feature from '../feature';

export default {
  components: {
    Feature,
  },
  setup() {
    const features = [
      {
        title: 'New Power',
        description: 'Start your journey and level up to 80, learning new powers and using them against your enemies. Empower them with glyphs and learn Dual Talent Specialization, so you can always be ready for your next battle.',
        icon: 'icon_power.svg',
        image: 'bg_power.png',
      },
      {
        title: 'Dungeon Finder',
        description: 'Find a group of allies to explore dungeons, striking down the threats that await you there. Get new, powerful items as you defeat the powerful foes with the help of other players.',
        icon: 'icon_dungeon-finder.svg',
        image: 'bg_dungeon-finder.png',
      },
      {
        title: 'Achievements',
        description: 'Track your progreression with Achievements, a system that rewards you for completing certain tasks, advancing your character, exploring the world and defeating powerful enemies. Gather mounts, pets, participate in the events and get exclusive mounts, pets and titles.',
        icon: 'icon_achievements.svg',
        image: 'bg_achievements.png',
      },
      {
        title: 'Northrend',
        description: 'Step into Northrend and face new enemies. Earn your trust within Kirin Tor, Argent Crusade and more enemies of the Scourge. Geaur up to raid the domains of the ancient foes, fight in the Argent Tournament and prepare to face the Lich King.',
        icon: 'icon_northrend.svg',
        image: 'bg_northrend.png',
      },
      {
        title: 'Arena',
        description: 'Fight your way to the top and participate in Arena Tournaments with grand prizes. Win prestigious titles, gaming gear and peripherals and become a legend.',
        icon: 'icon_arena.svg',
        image: 'bg_arena.png',
      },
      {
        title: 'Immersion',
        description: "Immerse yourself in a faithfully recreated world and enjoy all the smallest details you might have forgotten. Breath in the chilling, northern air and know that you're back home. Start your journey and experience the game in its former glory.",
        icon: 'icon_immersion.svg',
        image: 'bg_immersion.png',
      },
      {
        title: 'Community',
        description: 'Join over 35000 members of Atlantiss community, linked together by their love for World of Warcraft. Find new friends and guilds, participate in various contests and be a part of something big.',
        icon: 'icon_community.svg',
        image: 'bg_community.png',
      },
      {
        title: '...and more',
        description: "Participate in the Battle for the Undercity, take control over Wintergrasp, fight your way to the top of the arena charts, create a powerful Death Knight. Many challenges await you on Frozen Throne. Dance Studio included.",
        icon: 'icon_more.svg',
        image: 'bg_more.png',
      },
    ];

    return {
      features,
    }
  }
}
</script>

<style>
  .Features__list {
    width: 100%;
    margin: 0 auto;
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 2em 1.2em;
  }
</style>