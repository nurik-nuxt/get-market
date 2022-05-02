<template>
  <div class="category">
    <div class="category-title">Categories</div>
    <div class="category-list">
      <CategoryCard @clicked="productList" v-for="category in categories" :title="category.name" :id="category.id" style="justify-content: center; align-self: center; align-items: center"/>
    </div>
    <div class="category-bottom">
      <p>We’d love to hear what you think!</p>
      <div style="display: flex; justify-content: center">
        <button class="btn">Give Feedback</button>
      </div>
    </div>
  </div>
</template>
<script>
import CategoryCard from "@/components/common/Card/Category";
export default {
  components: {CategoryCard},
  data:() =>({
    categories:[]
  }),
  methods:{
    async fetchCategories(){
      await this.$axios.get('/api/categories')
        .then(res =>{
            console.log(res.data)
            this.categories = res.data.data
          }
        )
    },
    async productList(e){
      await this.$router.push(`/categories/${e}`)
    }
  },
  async mounted(){
    await this.fetchCategories()
  }

}
</script>

<style scoped lang="scss">
.category-list{
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-gap: 60px;
  justify-content: center;
  margin-bottom: 100px;
  margin-left: auto;
  margin-right: auto;
}
.category{
  display: flex;
  flex-direction: column;
}
.category-title{
  display: flex;
  flex-direction: row;
  justify-content: center;
  margin-bottom: 70px;
  font-family: 'Helvetica Now Display';
  font-style: normal;
  font-weight: 500;
  font-size: 20px;
  line-height: 29px;
  color: #757780;
}
.category-bottom{
  display: flex;
  flex-direction: column;
  justify-content: center;
  margin: 0;
  p{
    display: flex;
    flex-direction: row;
    justify-content: center;
    font-family: 'Helvetica Now Display';
    font-style: normal;
    font-weight: 400;
    font-size: 18px;
    line-height: 26px;
    margin: 0 0 25px 0;
    color: #000000;
  }
}
.btn{
  background: #387780;
  border-radius: 15px;
  max-width: 153px;
  display: flex;
  justify-content: center;
  font-family: 'Helvetica Now Display';
  font-style: normal;
  font-weight: 500;
  font-size: 18px;
  line-height: 26px;

  color: #FFFFFF;
}
</style>
