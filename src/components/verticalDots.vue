<template>
  <nav id="vertical-dots" role="navigation" aria-label="Navigation">
    <ul>
      <template v-for="(section, index) in sections">
        <li :key="index">
          <a class="v-dot-link" :href="'#'+section.section_id" :aria-labelledby="'v-dot-nav-section-'+index" :data-section="section.section_id">
            <span :id="'v-dot-nav-section-'+index">{{section.section_title}}</span>
            <i v-if="index===0" class="fas fa-arrow-up"></i>
          </a>
        </li>
      </template>
    </ul>
  </nav>
</template>

<script>

export default {
  name: 'verticalDots',
  props: {
    sections: {
      type: Array,
    },
  },
  data: function() {
    return {
      mainNavLinks: {},
      firstScroll: true
    }
  },
  created() {
    window.addEventListener("scroll", this.handleScroll);
  },
  methods: {
    handleScroll() {
      let fromTop = window.scrollY;
      if (this.firstScroll) {
        this.mainNavLinks = document.querySelectorAll("nav ul li a.v-dot-link");
        this.firstScroll = false;
      }

      this.mainNavLinks.forEach(link => {
          let section = document.querySelector(link.hash).parentNode.nextElementSibling;

          if (
              section.offsetTop -50 <= fromTop &&
              section.offsetTop -50 + section.offsetHeight > fromTop
          ) {
              link.classList.add("current");
          } else {
              link.classList.remove("current");
          }
      });
    }
  }
}
</script>

<style lang="scss">
@import '../../node_modules/@uiowa/uids/src/components/menus/vertical-dots/vertical-dots.scss';
</style>
