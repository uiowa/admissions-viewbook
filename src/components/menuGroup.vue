<template>
<nav role="navigation">
  <ul class="menu">
    <template v-for="(item, index) in items" :key="index">
      <menuItem
        :text="item.text"
        :url="item.url"
        :item_class="item.item_class"
        :icon_class="item.icon_class"
      />
    </template>
  </ul>
</nav>
</template>

<script>
import menuItem from './menuItem.vue';
export default {
    name: 'menuGroup',

    props: {
      items: {
        /*
          Array of items with the following structure:
          {
            text : String,
            url : String,
            item_class : String (Optional),
            icon_class : String (Optional)
          }
        */
        type: Array
      }
    },

    components: {
      menuItem
    }
}
</script>

<style lang="scss">
</style>