<template>
  <div class="filters">
    <h4>Kategorier</h4>
    <p v-for="filter in filters" :key="filter" @click="() => filterProducts(filter)" class="filters__item">
      {{ filter }}
    </p>
  </div>
</template>

<script>
const filters = [
  'Alle',
  'Dyr',
  'TV',
  'Film'
]

export default {
  props: [
    'filterProducts'
  ],
  data () {
    return {
      filters
    }
  }
}
</script>
