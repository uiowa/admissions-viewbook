<template>
<div class="logo" :class="logo_classes">
  <a href="https://uiowa.edu">
    <div class="element-invisible">The University of Iowa</div>
    <svg xmlns="http://www.w3.org/2000/svg" class="logo-icon" :aria-labelledby="IowaBarId(logo_id)" role="img" viewBox="0 0 311.6 90.2">
      <path class="st0" d="M40 18.8h-7.3v52.4H40v19H0v-19h7.3V18.8H0V0h40V18.8z"/>
      <path class="st0" d="M93.8 90.2h-29c-10.5 0-17.4-6.9-17.4-18.2V18.2C47.4 7 54.4 0 64.8 0h29c10.5 0 17.4 7 17.4 18.2V72C111.2 83.2 104.2 90.2 93.8 90.2zM85.6 71.2V18.8H73v52.4H85.6z"/>
      <path class="st0" d="M122.6 18.8h-6.4V0h38v18.9H147l6.5 43.4L167 0h19.2l14.4 62.3 5.2-43.4h-6.6V0h37.5v18.9h-6.2l-11.3 71.4h-30.6l-11.8-53.2 -12.1 53.1h-29.4L122.6 18.8z"/>
      <path class="st0" d="M230.1 71.2h6.9L250.7 0h41l13.5 71.2h6.4v19H281l-2.9-22h-15.2l-2.7 22h-30L230.1 71.2 230.1 71.2zM276.5 51.7l-5.8-36.4 -6 36.4H276.5z"/>
      <image src="../src/assets/uiowa-primary.png">
        <title :id="IowaBarId(logo_id)">University of Iowa</title>
      </image>
    </svg>
  </a>
</div>
</template>

<script>
export default {
    name: 'Logo',

    props: {
      logo_classes: {
        type: String
      },
      logo_id: {
        type: String
      }
    },

    methods: {
      /*
        This method takes a String 'logo_id'.
        It will return a String with either "logo-'logo_id' if 'logo_id' is set, and 'logo' if it is not.
      */
      IowaBarId(logo_id) {
        return (logo_id.length > 0) ? 'logo-' + logo_id : 'logo';
      }
    }
}
</script>

<style lang="scss">
@import '../../node_modules/@uiowa/uids/src/components/branding/logo/logo.scss';
</style>
