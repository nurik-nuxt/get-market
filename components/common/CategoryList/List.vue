<template>
  <div class="categories">
    <div class="categories__title">
      Shop by Categories
    </div>
<!--    <BaseIcon>electronics</BaseIcon>-->
    <div class="categories__list">
      <div v-for="category in categories" class="categories__list-item">
        <BaseIcon class="ic-70">{{category.icon}}</BaseIcon>
        <div class="categories__name">{{category.title}}</div>
      </div>
    </div>
  </div>
</template>
<script>
import BaseIcon from "~/components/base/BaseIcon";
export default {
  components: {BaseIcon},
  name:"CategoryList",
  data: () =>({
    categories:[
      {
        id:1,
        title:"Electronics",
        icon:'electronics'
      },
      {
        id:2,
        title:"Video Games",
        icon:'video-games'
      },
      {
        id:3,
        title:"Toys",
        icon:'toys'
      },
      {
        id:4,
        title:"Books",
        icon:'books'
      },
      {
        id:5,
        title:"Pet Supplies",
        icon:'pet'
      },
      {
        id:6,
        title:"Sports",
        icon:'sports'
      }

    ]
  })
}
</script>

<style scoped lang="scss">
.categories{
  display: flex;
  flex-direction: column;
  &__title{
    display: flex;
    flex-direction: row;
    justify-content: center;
    width: 100%;
    color: #757780;
    font-family: 'Helvetica Now Display';
    font-style: normal;
    font-weight: 500;
    font-size: 20px;
    line-height: 29px;
    text-decoration: underline;
    padding-bottom: 7px;
  }
  &__name{
    display: flex;
    justify-content: center;
    margin-top: 20px;
  }
  &__list{
    //display: flex;
    //flex-direction: row;
    //justify-content: space-between;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr;
    justify-content: center;
    grid-gap: 60px;
    margin: 60px 80px 80px 100px;
    &-item{
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      align-self: center;
    }
  }
}
</style>
