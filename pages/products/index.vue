<template>
  <div>
    <!--<p>Products</p>-->
    <div class="grid grid-cols-4 gap-5">
      <div v-for="product in products">
        <ProductCard :product="product" />
        <!--<NuxtLink :to="`/products/${product.id}`">{{ product.title }}</NuxtLink>-->
      </div>
    </div>
  </div>
</template>

<script>
  //import { onMounted } from 'vue'
  import ProductCard from '~/components/ProductCard.vue'

  export default {
    name: 'Index',
    components: { ProductCard },
    async setup() {
      definePageMeta({
        layout: 'products',
      })
      //onMounted(async () => {
      const { data: products } = await useFetch(
        'https://fakestoreapi.com/products'
      )
      //return products
      //})

      useHead({
        title: 'Nuxt Ninja | Merch',
        meta: [{ name: 'description', content: 'Nuxt 3 merch' }],
      })

      return { products }
    },
  }
</script>

<style scoped></style>
