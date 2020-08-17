<template>
  <div :class="grid_panel_type">
    <div :class="grid_panel_first_column">

      <div v-if="grid_content_position=='first'">
        <Headline 
          v-if="headline"
          heading_level="h2"
          class="bold-headline--caps bold-headline"
          :heading="headline"
        />

        <div v-html="grid_panel_content"></div>
        <div v-html="grid_panel_content_2"></div>
         <linkButton
            :button_link="button_link"
            button_type="bttn bttn--secondary bttn--caps"
            :button_text="button_text"
            :button_icon="true"
          />
      </div>
      <template v-if="grid_content_position=='second' && image!==''">
        <img :src="image" class="grid-panel__img" alt="">
      </template>
      <template v-else-if="grid_content_position=='second' && card_grid!==false">
        <div class="card__wrapper">
          <template v-for="(area, index) in areas_of_study">
            <hero
              :key="index"
              :hero_title="area.headline"
              :image="area.image"
              :url="area.link_url"
              :is_last="index+1 === areas_of_study.length"
              hero_overlay = "solid-opacity"
              hero_size="large"
              hero_classes="hero--row"
              hero_vertical_alignment="vertical-bottom"
              hero_horizontal_alignment="horizontal-left"
              hero_title_classes="bold-headline--caps bold-headline bold-headline--highlight"
            />
          </template>
        </div>
      </template>
    </div>
    <div :class="grid_panel_second_column">
      <div v-if="grid_content_position=='second'">
        <Headline
          v-if="headline"
          heading_level="h2"
          class="bold-headline--caps bold-headline"
          :heading="headline"
        />
        <div v-html="grid_panel_content"></div>
        <div v-html="grid_panel_content_2"></div>
        <linkButton
          :button_link="button_link"
          button_type="bttn bttn--secondary bttn--caps"
          :button_text="button_text"
          :button_icon="true"
        />
      </div>
      <template v-if="grid_content_position=='first' && image!==''">
        <img :src="image" class="grid-panel__img" alt="">
      </template>
      <template v-else-if="grid_content_position=='first' && card_grid!==false">
        <div class="card__wrapper">
          <template v-for="(area, index) in areas_of_study">
            <hero
              :key="index"
              :hero_title="area.headline"
              :image="area.image"
              :url="area.link_url"
              :hero_text="area.text"
              :button_text="area.button_text"
              :button_link="area.button_link"
              :is_last="index+1 === areas_of_study.length"
              hero_overlay = "solid-opacity"
              hero_size="large"
              hero_classes="hero--row"
              hero_vertical_alignment="vertical-bottom"
              hero_horizontal_alignment="horizontal-left"
              hero_title_classes="bold-headline--caps bold-headline bold-headline--highlight"
            />
          </template>
        </div>
      </template>
    </div>
  </div>
</template>

<script>
import Headline from './headline.vue';
import linkButton from './linkButton.vue';
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
        linkButton,
        Hero
    },
}
</script>

<style lang="scss">
    @import '../../node_modules/@uiowa/uids/src/components/grid-panel/grid-panel.scss';
</style>
