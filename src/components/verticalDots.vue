<template>
  <nav id="vertical-dots" role="navigation" aria-label="Navigation">
    <ul>
      <template :print="console.log(sections)" v-for="(section, index) in sections">
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
  }
}
</script>

<style lang="scss">
@import '../../node_modules/@uiowa/uids/src/components/menus/vertical-dots/vertical-dots.scss';
</style>
