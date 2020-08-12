<template>
<li class="menu-item">
  <a :href="url" :class="item_class">{{text}}</a>
  <!-- We would render submenu Items here -->
  <!-- {% if item.children %}
    {# If there is a child menu under this link, render it. #}
    {% include "@menu" with { items: item.children} %}
  {% endif %} -->
</li>
</template>

<script>
export default {
    props: ['text', 'url', 'item_class'],
}
</script>

<style lang="scss">
</style>