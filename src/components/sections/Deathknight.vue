<template>
  <section id="deathknight">
    <header>
      <span class="section-name">{{sectionName}}</span>
      <h2>{{title}}</h2>
    </header>
    <article>
      <div class="row">
        <div class="column">
          <h3>Heralds of Doom</h3>
          <p>
            Champions in life, servants in undeath. Arthas has broken once noble heroes and remade them in his image. Death Knights serve the Lich King in his aim to bring all of Azeroth down to its knees.
          </p>
          <br />
          <p>
            Control can not always be maintained. Once broken from Arthas' grasp, they seek revenge on the fallen prince for the horrors they committed under his will. Driven by vengeance, they will not stop until the Lich King falls.
          </p>
        </div>
        <div class="column">
          <figure>
            <img
              class="Deathknight__img"
              alt="Death knight"
              src="../../assets/images/deathknight/dk.jpg"
              @click="setIsOpen($event, true)" />
          </figure>
        </div>
      </div>
      <div class="row">
        <div class="column">
          <Talents />
        </div>
        <div class="column">
          <h3>Masters of the Battlefield</h3>
          <p>
            Empowered by the Lich King himself, Death Knights know no pain, no mercy, no exhaustion. Through Blood they become an unstoppable force, with Frost they strike down their enemies, and their Unholy power lets them command the undead and bend them to their will.
          </p>
        </div>
      </div>
      <div class="row">
        <div class="column">
          <h3>Mount the Dead</h3>
          <p>
            Ride to battle on the back of your Deathcharger and soar the skies on top of Skeletal Gryphon, unique mounts available only to the Death Knights.
          </p>
          <p class="quote">
            „Some gryphons merely adopted the dark. This one was born in it, molded by it.”
          </p>
        </div>
        <div class="column">
          <figure>
            <img
              class="Deathknight__img"
              src="../../assets/images/deathknight/dk-mount.png"
              alt="Death knight mount"
              @click="setIsOpen($event, true)" />
          </figure>
        </div>
      </div>
    </article>
    <div
      v-show="isOpen"
      class="fullscreen"
      @click="setIsOpen(false)"
      @click.stop="">
      <div id="fullscreenWrapper" ref="fullscreenWrapper"></div>
    </div>
  </section>
</template>

<script>
import { ref, reactive, toRefs, onMounted } from 'vue';
import Talents from '../deathknight/talents';

export default {
  components: {
    Talents,
  },
  props: {
    sectionName: String,
    title: String,
  },
  setup() {
    const fullscreenWrapper = ref(null);
    const state = reactive({
      isOpen: false,
    });

    function setIsOpen($event, val) {
      state.isOpen = val;

      if (state.isOpen) {
        fullscreenWrapper.value.textContent = '';

        const imageCopy = $event.target.cloneNode(true);
        imageCopy.addEventListener('click', e => {
          e.stopPropagation();
        })
        fullscreenWrapper.value.append(imageCopy);
      }
    }

    onMounted(() => {
      console.log(fullscreenWrapper.value)
    })
    
    return {
      fullscreenWrapper,
      setIsOpen,
      ...toRefs(state),
    }
  }
}
</script>

<style>
  .Deathknight__img {
    width: 100%;
    box-shadow: 0 0 32px 0 rgba(0, 0, 0, .8);
    margin-bottom: 1em;
    object-fit: contain;
  }

  .fullscreen {
    position: fixed;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    width: 100%;
    height: 100vh;
    background: rgba(0, 0, 0, 0.8);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 10;
    transition: all 300ms ease;
  }
  .fullscreen .Deathknight__img {
    max-width: 90vmin;
  }
</style>