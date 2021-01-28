<template>
  <footer class="Footer">
    <div class="Footer__content">
      <div>
        <SectionLinks :links="links" />
        <ul class="Footer__social-media">
          <li><DiscordLink /></li>
          <li><GithubLink /></li>
        </ul>
      </div>
      <div class="Footer__bottom">
        <div></div>
        <div class="Footer__copyright">
          <span>{{copyright}}</span>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
import DiscordLink from '../social-media/DiscordLink.vue';
import GithubLink from '../social-media/GithubLink.vue';
import SectionLinks from '../section-links';
import LinkData from '../../data/link-data';

export default {
  name: 'Footer',
  components: {
    DiscordLink,
    GithubLink,
    SectionLinks,
  },
  props: {
    copyright: String,
  },
  setup() {
    const links = LinkData;

    return {
      links,
    }
  }
}
</script>

<style>
  .Footer {
    position: absolute;
    bottom: 0;
    width: 100%;
    min-height: 200px;
    background: black;
    padding: 0 15px;
  }

  .Footer__content {
    margin: 40px auto;
    max-width: var(--page-max-width);
    display: flex;
    flex-direction: column;
    align-items: space-between;
    gap: 40px;
  }

  .Footer__content > div {
    display: flex;
    justify-content: space-between;
    gap: 40px;
  }

  .Footer__social-media {
    display: flex;
    gap: 15px;
  }

  .Footer__bottom {
    gap: 30px;
  }

  .Footer__copyright {
    opacity: 0.8;
    font-size: 0.9rem;
  }
</style>