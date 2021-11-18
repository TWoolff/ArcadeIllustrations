<template>
  <router-view :products="products" />
  <nav>
    <router-link to="/">Forside</router-link> |
    <router-link to="/about">Om Arcade Illustrations</router-link> |
    <router-link to="/contact">Kontakt</router-link> |
    <Filters :filterProducts="filterProducts" />
    <div @click="toggleSidebar" class="nav-cart">Kurv</div>
  </nav>
  <transition name="side">
    <Sidebar v-if="showSidebar" :toggle="toggleSidebar" header="Kurv" />
  </transition>
</template>

<script>
import products from '@/products.json'
import Sidebar from '@/components/Sidebar'
import Filters from '@/components/Filters'

export default {
  components: { Sidebar, Filters },
  data () {
    return {
      products: products,
      showSidebar: false,
      cart: {}
    }
  },
  methods: {
    toggleSidebar () {
      this.showSidebar = !this.showSidebar
    },
    filterProducts (catName) {
      this.products = products
      if (catName !== 'Alle') {
        this.products = this.products.filter((product) => {
          return product.category === catName
        })
      }
    }
  }
}
</script>
