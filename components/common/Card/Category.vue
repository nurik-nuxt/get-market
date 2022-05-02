<template>
  <div @click="toProduct(id)" class="category-card">
    <BaseIcon>{{icon}}</BaseIcon>
    <div class="category-card__title">{{title}}</div>
  </div>
</template>

<script>
import BaseIcon from "@/components/base/BaseIcon";
export default {
  name:"CategoryCard",
  components: {BaseIcon},
  methods:{
    toProduct(e){
      this.$emit('clicked',e)
    }
  },
  data:() =>({

  }),
  props:{
    title:{
      type:String,
      default:"Electronics"
    },
    icon:{
      type:String,
      default:'electronics'
    },
    id:{
      type: Number
    }
  }
}
</script>

<style scoped lang="scss">
.category-card{
  display: flex;
  flex-direction: column;
  max-width: 300px;
  height: 285px;
  align-items: center;
  align-self: center;
  border: 2px solid #EEEFF0;
  justify-content: center;
  box-shadow: 0 10px 10px 0 #aaaaaa;
  &__title{
    display: flex;
    justify-content: center;
    margin-top: 30px;
  }
}
</style>
