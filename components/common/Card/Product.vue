<template>
  <div class="product">
    <div class="product__image">
      {{image}}
    </div>
    <div class="product__price">
      {{price}}
    </div>
    <div class="product__title">{{title}}</div>
  </div>
</template>

<script>
  export default {
    name:"ProductCard",

    props:{
      image:{
        type:String
      },
      price:{
        type:String,
        default:"94000"
      },
      title:{
        type:String,
        default: "Apple iPhone 11 128GB Black"
      }
    }
  }
</script>

<style scoped lang="scss">
.product{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-self: center;
  //align-items: center;
  &__image{
    background: #757780;
    border-radius: 10px;
    max-width: 180px;
    height: 220px;
  }
  &__price{
    margin-top: 15px;
    font-family: 'Helvetica Now Display';
    font-style: normal;
    font-weight: 600;
    font-size: 18px;
    line-height: 26px;
    color: #000000;
  }
  &__title{
    margin-top: 15px;
  }
}
</style>
