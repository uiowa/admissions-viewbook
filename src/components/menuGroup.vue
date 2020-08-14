<template>
<nav role="navigation">
  <ul class="menu">
    <template v-for="(item, index) in items">

      {{clog(item)}}
      <menuItem
        :key="index"
        :text="item.text"
        :url="item.url"
        :item_class="item.item_class"
        :icon_class="item.icon_class"
      >
      </menuItem>
    </template>
  </ul>
</nav>
</template>

<script>
import menuItem from './menuItem.vue';
export default {
    props: ['items'],
    components: {
      menuItem
    },
    methods: {
      clog(a) {
        console.log(a);
      }
    }
}
</script>

<style lang="scss">
</style>