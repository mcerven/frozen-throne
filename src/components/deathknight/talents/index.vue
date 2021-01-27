<template>
  <div class="Talents">
    <Talent v-for="talent in talents"
      :key="talent.name"
      :name="talent.name"
      :role="talent.role"
      :image="talent.image"
      />
  </div>
</template>

<script>
import Talent from './Talent';

export default {
  name: 'Talents',
  components: {
    Talent,
  },
  setup() {
    const talents = [
      {
        name: 'Blood',
        role: 'Tank',
        image: 'blood.jpg',
      },
      {
        name: 'Frost',
        role: 'Damage Dealer',
        image: 'frost.jpg',
      },
      {
        name: 'Unholy',
        role: 'Damage Dealer',
        image: 'unholy.jpg',
      },
    ];
    return {
      talents,
    }
  }
}
</script>

<style>
  .Talents {
    display: flex;
    flex-direction: column;
    gap: 10px;
  }
</style>