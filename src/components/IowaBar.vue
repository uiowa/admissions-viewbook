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
    props: ['iowa_bar_classes', 'parent_site'],
    components: {
      Logo
    },
    methods: {
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