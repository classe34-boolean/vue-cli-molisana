<template>
  <div class="card">
     <img :src="singleProduct.src" :alt="singleProduct.titolo">
  </div>
</template>

<script>
export default {
    name: "Card",
    props: ["singleProduct"]
}
</script>

<style lang="scss">
    .card {
        width: calc(100% / 3);
        img {
            display: block;
        }
    }
</style>