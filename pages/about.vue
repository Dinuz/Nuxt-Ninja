<template>
  <div>
    <h2>About</h2>
    <p>
      Dictas ei alienum vestibulum sea constituam consequat. Dolores praesent
      alterum persequeris vidisse elitr in. Dictas explicari alienum movet
      sapientem vulputate platonem. Penatibus explicari expetenda venenatis
      feugait vivendo brute docendi contentiones postulant. Epicuri duo
      signiferumque persecuti porttitor torquent dicat donec.
    </p>
    <p>
      Dictas ei alienum vestibulum sea constituam consequat. Dolores praesent
      alterum persequeris vidisse elitr in. Dictas explicari alienum movet
      sapientem vulputate platonem. Penatibus explicari expetenda venenatis
      feugait vivendo brute docendi contentiones postulant. Epicuri duo
      signiferumque persecuti porttitor torquent dicat donec.
    </p>
    <div>{{ data }}</div>
  </div>
</template>

<!--<script setup>
  const { data } = await useFetch('/api/ninja')
</script>-->
<script>
  export default {
    // eslint-disable-next-line vue/multi-word-component-names
    name: 'About',
    async setup() {
      //const { data } = await useFetch('/api/ninja?name=mario', {
      //  method: 'post',
      //  body: { age: 30 },
      //})

      const { data } = await useFetch('/api/currency/GBP')

      return { data }
    },
  }
</script>

<style scoped>
  h2 {
    margin-bottom: 20px;
    font-size: 36px;
  }

  p {
    margin: 20px 0;
  }
</style>
