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
      <template v-if="grid_content_position=='second' && image!==''">
        <img :src="image" class="grid-panel__img" alt="">
      </template>
      <template v-else-if="grid_content_position=='second' && card_grid!==false">
        <div class="card__wrapper">
          <template v-for="(area, index) in areas_of_study">
            <hero :key="index"
                  :headline="area.headline"
                  :image="area.image"
                  :url="area.link_url"
                  :class="getHeroClasses(index)"
            >
            </hero>
          </template>
        </div>
      </template>
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
      <template v-if="grid_content_position=='first' && image!==''">
        <img :src="image" class="grid-panel__img" alt="">
      </template>
      <template v-else-if="grid_content_position=='first' && card_grid!==false">
        <div class="card__wrapper">
          <template v-for="(area, index) in areas_of_study">
            <hero :key="index"
                  :headline="area.headline"
                  :image="area.image"
                  :url="area.link_url"
                  :is_last="index+1 === areas_of_study.length"
            >
            </hero>
          </template>
        </div>
      </template>
    </div>
  </div>
</template>

<script>
import Headline from './headline.vue';
import uidsButton from './uidsButton.vue';
import Hero from './Hero.vue';
export default {
    props: [
      'grid_panel_type',
      'button_text',
      'button_link',
      'grid_panel_first_column',
      'grid_panel_second_column',
      'grid_panel_content',
      'grid_panel_content_2',
      'grid_content_position',
      'headline',
      'image',
      'link_url',
      'card_grid',
      'areas_of_study'
    ],
    components: {
        Headline,
        uidsButton,
        Hero

    },
}
</script>

<style lang="scss">
    @import '../../node_modules/@uiowa/uids/src/components/grid-panel/grid-panel.scss';
</style>
