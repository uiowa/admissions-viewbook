<template>
  <div :class="grid_panel_type">
    <div :class="grid_panel_first_column">

      <div v-if="grid_content_position=='first'">
        <Headline 
          v-if="headline"
          headline_level="h2"
          class="headline headline--uppercase"
          :headline="headline"
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
        <img :src="image" class="grid-panel__img" alt="" loading="lazy">
      </template>
      <template v-else-if="grid_content_position=='second' && card_grid!==false">
        <div class="grid--threecol--33-34-33">
          <div class="list-container">
          <template v-for="(area, index) in areas_of_study" :key="index">
            <banner
              :banner_title="area.headline"
              :image="area.image"
              :link_url="area.link_url"
              :is_last="index+1 === areas_of_study.length"
              banner_overlay = "solid-opacity"
              banner_size="large"
              banner_classes="hero--row"
              banner_vertical_alignment="vertical-bottom"
              banner_horizontal_alignment="horizontal-left"
              banner_title_classes="headline headline--uppercase headline--highlight"
            />
          </template>
          </div>
        </div>
      </template>
    </div>
    <div :class="grid_panel_second_column">
      <div v-if="grid_content_position=='second'">
        <Headline
          v-if="headline"
          headline_level="h2"
          class="headline headline--uppercase"
          :headline="headline"
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
        <img :src="image" class="grid-panel__img" alt="" loading="lazy">
      </template>
      <template v-else-if="grid_content_position=='first' && card_grid!==false">
        <div class="grid--threecol--33-34-33">
          <div class="list-container">
          <template v-for="(area, index) in areas_of_study" :key="index">
            <banner
              :banner_title="area.headline"
              :image="area.image"
              :link_url="area.link_url"
              :banner_text="area.text"
              :button_text="area.button_text"
              :button_link="area.button_link"
              :is_last="index+1 === areas_of_study.length"
              banner_overlay = "solid-opacity"
              banner_size="small"
              banner_classes="banner--row"
              banner_vertical_alignment="vertical-bottom"
              banner_horizontal_alignment="horizontal-left"
              banner_title_classes="headline headline--uppercase headline--highlight"
            />
          </template>
        </div>
        </div>
      </template>
    </div>
  </div>
</template>

<script>
import Headline from './Headline.vue';
import linkButton from './linkButton.vue';
import Banner from './Banner.vue';
export default {
    name: 'GridPanel',

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
        Banner
    },
}
</script>

<style lang="scss">
    @import '../../node_modules/@uiowa/uids/src/components/viewbook/grid-panel/grid-panel.scss';
</style>
