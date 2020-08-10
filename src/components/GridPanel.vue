<template>
  <div :class="grid_panel_type">
    <div :class="grid_panel_first_column">

      <div v-if="grid_content_position=='first'">
        <headline v-if="headline"
                  heading_level="h2"
                  class="bold-headline--caps bold-headline"
                  :heading="headline"
                  :heading_url="link_url">
        </headline>

        <div v-html="grid_panel_content"></div>
        <div v-html="grid_panel_content_2"></div>
      </div>
      <div v-if="grid_content_position=='second'">
        <img :src="image" class="grid-panel__img" alt="">
      </div>
    </div>
    <div :class="grid_panel_second_column">
      <div v-if="grid_content_position=='second'">
        <headline v-if="headline"
                  heading_level="h2"
                  class="bold-headline--caps bold-headline"
                  :heading="headline">
        </headline>
        <div v-html="grid_panel_content"></div>
        <div v-html="grid_panel_content_2"></div>
        <uids-button
            :button_link="button_link"
            button_type="bttn bttn--secondary bttn--caps"
            :button_text="button_text"
            :button_icon="true">
        </uids-button>
      </div>
      <div v-if="grid_content_position=='first'">
        <img :src="image" class="grid-panel__img" alt="">
      </div>
    </div>
  </div>
</template>

<script>
import Headline from './headline.vue';
import uidsButton from './uidsButton.vue';
export default {
    props: ['grid_panel_type',  'button_text', 'button_link', 'grid_panel_first_column', 'grid_panel_second_column', 'grid_panel_content', 'grid_panel_content_2', 'grid_content_position', 'headline', 'image', 'link_url'],
    components: {
        Headline,
        uidsButton,
    },
}
</script>

<style lang="scss">
    @import '../../node_modules/@uiowa/uids/src/components/grid-panel/grid-panel.scss';
</style>
