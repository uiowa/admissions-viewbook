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
    name: 'Stat',

    props: {
      headline: {
        type: String
      },
      heading_prefix: {
        type: String
      },
      heading_suffix: {
        type: String
      },
      image: {
        type: String
      },
      link_url: {
        type: String
      },
      stat_description: {
        type: String
      },
      stat_content: {
        type: String
      }
    },

    components: {
        Headline,
    }
}
</script>

<style lang="scss">
    @import '../../node_modules/@uiowa/uids/src/components/stat/stat.scss';
</style>
