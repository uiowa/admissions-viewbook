<template>
<div class="highlight__wrapper">
  <Headline v-if="typeof highlight_title !== 'undefined'"
    heading_level= "h3"
    heading_class= "highlight__title"
    :heading="highlight_title"
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
  props: ['headline_level', 'highlight_title', 'highlight_sub']
}
</script>

<style lang="scss">
@import '../../node_modules/@uiowa/uids/src/components/highlight/highlight.scss';
</style>
