<template>
<nav role="navigation">
  <ul class="menu">
    <template v-for="(item, index) in items">
      <menuItem
        :key="index"
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
    props: ['items'],
    components: {
      menuItem
    }
}
</script>

<style lang="scss">
</style>