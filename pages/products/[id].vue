<template>
  <div>
    <Head>
      <Title>Nuxt Ninja | {{ product.title }}</Title>
      <Meta name="description" :content="product.description"></Meta>
    </Head>
    <ProductDetails :product="product" />
  </div>
</template>

<script>
  export default {
    name: '[id]',
    async setup() {
      definePageMeta({
        layout: 'products',
      })

      const { id } = useRoute().params

      const uri = 'https://fakestoreapi.com/products/' + id

      const { data: product } = await useFetch(uri, { key: id })

      if (!product.value) {
        throw createError({
          statusCode: 404,
          statusMessage: 'Product not found',
          fatal: true,
        })
      }

      return {
        id,
        product,
      }
    },
  }
</script>

<style scoped></style>
