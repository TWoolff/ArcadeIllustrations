<template>
  <transition-group tag="div" name="cards" appear>
    <div v-for="product in products" :key="product.id" class="card">
      <img :src="'/img/' + product.image + '.jpg'" :alt="product.image">
    </div>
  </transition-group>
</template>

<script>

export default {
  props: ['products']
}
</script>
