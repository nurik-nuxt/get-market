<template>
  <div class="for-you">
    <div class="for-you__title">
      For You
    </div>
    <div class="for-you__content">
      <div class="for-you__one">A</div>
      <div class="for-you__two">B</div>
      <div class="for-you__three">C</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ForYou"
}
</script>

<style scoped lang="scss">
.for-you{
  background: #E3E4DB;
  &__title{
    display: flex;
    flex-direction: row;
    justify-content: center;
    padding: 20px 0;
  }
  &__one{
    max-width: 560px;
    background: #757780;
    border-radius: 10px;
    grid-row: 1/3;
    display: flex;
    justify-content: center;
    height: 460px;
  }
  &__two{
    max-width: 560px;
    background: #757780;
    border-radius: 10px;
    grid-row: 1/3;
    display: flex;
    justify-content: center;
    height: 220px;
  }
  &__three{
    max-width: 560px;
    background: #757780;
    border-radius: 10px;
    grid-column: 2/3;
    display: flex;
    justify-content: center;
    height: 220px;
  }
  &__content{
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 1fr 1fr;
    padding: 0 60px;
  }
}
</style>
