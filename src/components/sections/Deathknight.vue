<template>
  <section id="deathknight">
    <header>
      <h2>New class - Death knight</h2>
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
            <img class="Deathknight__img" alt="Death knight"
              src="../../assets/images/deathknight/dk.jpg" />
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
            <img class="Deathknight__img" alt="Death knight mount"
              src="../../assets/images/deathknight/dk-mount.png" />
          </figure>
        </div>
      </div>
    </article>
  </section>
</template>

<script>
import Talents from '../deathknight/talents';

export default {
  components: {
    Talents,
  }
}
</script>

<style>
  .Deathknight__img {
    width: 600px;
    box-shadow: 0 0 30px 0 rgba(0, 0, 0, .8);
    margin-bottom: 1em;
  }
</style>