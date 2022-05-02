<template>
  <div class="products">
    <div class="title">
      <p>Home / Categories / {{id}}</p>
    </div>
    <div class="popular-products">
      <ProductCard
        v-for="product in products"
        :title="product.name"
        :price="product.price"
      />
    </div>
  </div>
</template>

<script>

import ProductCard from "@/components/common/Card/Product";
export default {
  components: {ProductCard},
  computed:{
    id(){
      return this.$route.params.id
    }
  },
  data:() => ({
    products:[]
  }),
  methods:{
    async fetchProducts(){
      await this.$axios.$get('/api/products')
        .then(res => {
          this.products = res.data
          console.log(res.data)
        })
    }
  },
  async mounted(){
    await this.fetchProducts()
  }
}
</script>

<style scoped lang="scss">
.popular-products{
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
  margin-left: 60px;
  margin-right: 60px;
  grid-gap: 60px;
  justify-content: center;
  margin-bottom: 100px;
}
.products{
  margin-top: 25px;
}
.title{
  margin-left: 60px;
}
</style>
