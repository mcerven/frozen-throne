<template>
  <section id="king">
    <header>
      <h2>{{title}}</h2>
    </header>
    <div class="container">
      <div class="KingReturn">
        <iframe
          class="KingReturn__cinematic"
          :title="title"
          :src="videoUrl"
          frameBorder="0"
          allowFullScreen
        />
      </div>
    </div>
    <footer class="Footer">
      <div class="Footer__content"></div>
    </footer>
  </section>
</template>

<script>
export default {
  props: {
    title: String,
    videoUrl: String,
  },
}
</script>

<style>
  .container {
    max-width: 1200px;
    margin: 0 auto;
  }

  .KingReturn {
    display: flex;
    justify-content: center;
  }

  .KingReturn__cinematic {
    width: 800px;
    height: 450px;
  }
  
  .Footer {
    position: absolute;
    bottom: 0;
    width: 100%;
    height: 200px;
    background: black;
  }

  .Footer__content {
    margin: 0 auto;
    max-width: 1200px;
  }
</style>