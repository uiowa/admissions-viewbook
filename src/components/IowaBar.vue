<template>
  <header class="iowa-bar" :class="IowaBarClasses()">
    <div class="iowa-bar__container">
      <logo
        logo_id="header"
        logo_classes="logo--tab"
      />
      <!-- This is where we would print a parent site name or an inline site name -->
      <!-- This is where we would print Top links -->
      <!-- This is where we would print off canvas -->
    </div>
    <!-- this is where we would print below bar content -->
  </header>
</template>

<script>
import Logo from './Logo.vue';

export default {
    name: 'IowaBar',

    props: {
      iowa_bar_classes: {
        type: String
      },
      parent_site: {
        type: String
      }
    },

    components: {
      Logo
    },

    methods: {
      // This method will default the iowa bar to narrow if there is a parent site set.
      IowaBarClasses() {
        if (typeof this.$props.parent_site !== "undefined" ) {
          return (this.$props.iowa_bar_classes + ' ' + 'iowa-bar--narrow');
        }
        else {
          return this.$props.iowa_bar_classes;
        }
      }
    }
}
</script>

<style lang="scss">
@import '../../node_modules/@uiowa/uids/src/components/branding/iowa-bar/iowa-bar.scss';
</style>