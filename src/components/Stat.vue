<template>
  <div class="stat__grid stat--horizontal">
    <div>
      <Headline
        v-if="headline"
        heading_level="h2"
        class="stat__title"
        :heading="headline"
        :heading_prefix="heading_prefix"
        :heading_suffix="heading_suffix"
      />
    </div>
    <p v-html="stat_description" class="stat__description"></p>
    <p v-html="stat_content" class="stat__content"></p>
  </div>
</template>

<script>
import Headline from './headline.vue';

export default {
    props: ['headline', 'heading_prefix', 'heading_suffix', 'image', 'link_url', 'stat_description', 'stat_content'],
    components: {
        Headline,
    }
}
</script>

<style lang="scss">
    @import '../../node_modules/@uiowa/uids/src/components/stat/stat.scss';
</style>
