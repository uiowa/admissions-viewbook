<template>
    <component :is="headline_level" :class="headline_class">
        <a v-if="headline_url" :href="headline_url" :aria-describedby="headline_aria ? headline_aria :''">
            <span v-if="headline_prefix" class="headline__prefix">{{headline_prefix}}</span>
            <span v-html="headline" class="headline__text"></span>
            <span v-if="headline_suffix" class="headline__suffix">{{headline_suffix}}</span>
        </a>
        <template v-else>
            <span v-if="headline_prefix" class="headline__prefix">{{headline_prefix}}</span>
            <span v-html="headline" class="headline__text"></span>
            <span v-if="headline_suffix" class="headline__suffix">{{headline_suffix}}</span>
        </template>
    </component>
</template>

<script>

export default {
  name: 'Headline',
  
  props: {
    headline_level: {
      type: String,
    },
    headline_class: {
      type: String,
    },
    headline: {
      type: String,
    },
    headline_url: {
      type: String,
    },
    headline_aria: {
      type: String,
    },
    headline_prefix: {
      type: String,
    },
    headline_suffix: {
      type: String,
    },
  }
}
</script>

<style lang="scss">
@import '../../node_modules/@uiowa/uids/src/components/headline/headline.scss';
@import '../../node_modules/@uiowa/uids/src/components/typography/headings/headings.scss';
.headline__suffix {
  padding-left: .5rem;
}
.headline__prefix {
  padding-right: .5rem;
}
</style>
