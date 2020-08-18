<template>
<component :is="site_name_tag ? site_name_tag : 'h1'" class="site-name">
  <a v-if="site_name_link" :href="site_name_link">{{site_name}}</a>
  <template v-else>{{site_name}}</template>
</component>
</template>

<script>
export default {
    name: 'siteName',

    props: {
      site_name: {
        type: String
      },
      site_name_tag: {
        type: String
      },
      site_name_link: {
        type: String
      }
    },
}
</script>

<style lang="scss">
@import '../../node_modules/@uiowa/uids/src/components/branding/site-name/site-name.scss';
</style>