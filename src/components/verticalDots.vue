<template>
  <nav id="vertical-dots" role="navigation" aria-label="Navigation">
    <ul>
      <template v-for="(section, index) in sections" :key="index">
        <li>
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
      /*
        Array of items with the following structure:
        {
          section_title: String,
          section_id: 'String
        }
      */
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
    // Call 'handleScroll()' on every 'scroll' event.
    window.addEventListener("scroll", this.handleScroll);
  },

  methods: {
    // This method will be called on every scroll event on the document.
    handleScroll() {
      // Deterine how far from the top of the document the window is.
      let fromTop = window.scrollY;

      // If this is the first scroll, get the vertical dots nav components.
      if (this.firstScroll) {
        this.mainNavLinks = document.querySelectorAll("nav ul li a.v-dot-link");
        this.firstScroll = false;
      }

      // Look through each link.
      this.mainNavLinks.forEach(link => {
        // Get the v-dots-scroll-spacer defined by the href on the vertical dot and thenselect the section directly after it.
        let section = document.querySelector(link.hash).parentNode.nextElementSibling;
        /*
          The spacer tries to accomodate for the Iowa bar height, so it is absolutely pushed up 50px.
          Here, we accomodate for that by checking the offset minus 50.
        */
        if (
          section.offsetTop -50 <= fromTop &&
          section.offsetTop -50 + section.offsetHeight > fromTop
        ) {
          // If we are on the section that is in the viewport, add the class 'current' to the vertical dot.
          link.classList.add("current");
        } else {
          // Else, we remove 'current'.
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
