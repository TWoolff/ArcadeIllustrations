<template>
  <aside class="sidebar">
    <h4>{{ header }}</h4>
    <button @click="toggle" class="cart-close">&times;</button>
  </aside>
</template>

<script>
export default {
  props: ['toggle', 'header']
}
</script>
