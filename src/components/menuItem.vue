<template>
<li class="menu-item">
  <a :href="url" :class="item_class">
    <template v-if="icon_class">
      <i :class="icon_class"></i><span class="link-text">{{text}}</span>
    </template>
    <template v-else>
      {{text}}
    </template>
  </a>
  <!-- We would render submenu Items here -->
</li>
</template>

<script>
export default {
    name: 'menuItem',

    props: {
      text: {
        type: String
      },
      url: {
        type: String
      },
      item_class: {
        type: String
      },
      icon_class: {
        type: String
      }
    },
}
</script>

<style lang="scss">
</style>