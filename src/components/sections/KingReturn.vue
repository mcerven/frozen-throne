<template>
  <section id="king">
    <header>
      <h2>{{title}}</h2>
    </header>
    <div class="KingReturn">
      <div class="KingReturn__cinematic">
        <iframe
          :title="title"
          :src="videoUrl"
          frameBorder="0"
          allowFullScreen
        />
      </div>
    </div>
    <Footer :copyright="copyright" />
  </section>
</template>

<script>
import Footer from '../footer';

export default {
  components: {
    Footer,
  },
  props: {
    title: String,
    videoUrl: String,
    copyright: String,
  },
}
</script>

<style>
  .KingReturn {
    max-width: 1200px;
    margin: 0 auto;
  }

  .KingReturn__cinematic {
    display: flex;
    justify-content: center;
    padding: 0 10px;
  }

  .KingReturn__cinematic iframe {
    width: 800px;
    height: 450px;
  }

  @media
    screen and (max-width: 850px),
    screen and (max-height: 800px) {
    .KingReturn__cinematic iframe {
      width: 600px;
      height: 340px;
    }
  }
</style>