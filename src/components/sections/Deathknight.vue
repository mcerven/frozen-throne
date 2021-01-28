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
              alt="Death Knight"
              src="../../assets/images/deathknight/dk.jpg"
              @click="setIsOpen($event, true)" />
          </figure>
        </div>
      </div>
      <div class="row Deathknight__talents-column">
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
              alt="Death Knight Class Mount"
              @click="setIsOpen($event, true)" />
          </figure>
        </div>
      </div>
    </article>
    <div
      v-show="isOpen"
      class="modal"
      @click="setIsOpen(false)"
      @click.stop="">
      <button class="modal-close" type="button" @click="setIsOpen(false)">&times;</button>
      <div id="modalContent" ref="modalContent"></div>
    </div>
  </section>
</template>

<script>
import { ref, reactive, toRefs, onMounted } from 'vue';
import Talents from '../deathknight/talents';

export default {
  name: 'Deathknight',
  components: {
    Talents,
  },
  props: {
    sectionName: String,
    title: String,
  },
  setup() {
    const modalContent = ref(null);
    const state = reactive({
      isOpen: false,
    });

    function setIsOpen($event, val) {
      state.isOpen = val;

      if (state.isOpen) {
        modalContent.value.textContent = '';

        const imageCopy = $event.target.cloneNode(true);
        imageCopy.addEventListener('click', e => {
          e.stopPropagation();
        })
        modalContent.value.append(imageCopy);
        modalContent.value.append(imageCopy.alt);
      }
    }

    onMounted(() => {
      console.log(modalContent.value)
    })
    
    return {
      modalContent,
      setIsOpen,
      ...toRefs(state),
    }
  }
}
</script>

<style>
  .Deathknight__talents-column {
    flex-wrap: wrap-reverse;
  }

  .Deathknight__img {
    width: 100%;
    box-shadow: 0 0 32px 0 rgba(0, 0, 0, .8);
    object-fit: contain;
    user-select: none;
    cursor: pointer;
    display: block;
  }

  .modal {
    position: fixed;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    background: rgba(0, 0, 0, 0.8);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 10;
  }

  .modal-close {
    position: absolute;
    top: 20px;
    right: 35px;
    color: #ccc;
    font-size: 40px;
    font-weight: bold;
    user-select: none;
    transition: 0.3s;
    background: transparent;
    border: none;
    width: 2rem;
    height: 2rem;
    display: flex;
    justify-content: center;
    align-items: center;
    outline: none;
  }

  .modal-close:hover,
  .modal-close:focus {
    color: #ffffff;
    text-decoration: none;
    cursor: pointer;
  }

  #modalContent {
    font-size: 0.85rem;
    width: 90%;
    max-width: var(--page-max-width);
    height: 90%;
    max-height: 90%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 0.5rem;
    animation: appear 400ms ease-out;
  }

  #modalContent img {
    cursor: default;
    max-height: calc(100% - 2rem);
  }

  @keyframes appear {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }
</style>