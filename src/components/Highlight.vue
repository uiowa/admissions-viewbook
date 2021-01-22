<template>
<div class="highlight__wrapper">
  <Headline v-if="typeof highlight_title !== 'undefined'"
    headline_level= "h3"
    headline_class= "highlight__title"
    :headline="highlight_title"
  />
  <div v-if="typeof highlight_sub !== 'undefined'" class="highlight__sub">
    <span>{{ highlight_sub }}</span>
  </div>
</div>
</template>

<script>
import Headline from './Headline.vue';

export default {
  name: 'Highlight',

  components: {
    Headline
  },

  props: {
    headline_level: {
      type: String
    },
    highlight_title: {
      type: String
    },
    highlight_sub: {
      type: String
    }
  }
}
</script>

<style lang="scss">
@import '../../node_modules/@uiowa/uids/src/components/highlight/highlight.scss';
</style>
