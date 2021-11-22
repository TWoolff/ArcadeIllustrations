<template>
  <section class="home">
    <Card :products="products" class="home__content" />
  </section>
</template>

<script>
import Card from '@/components/Card'

export default {
  name: 'Home',
  props: ['products'],
  components: { Card }
}
</script>
