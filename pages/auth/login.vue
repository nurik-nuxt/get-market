<template>
  <div class="registration">
    <p>Sign in to your account</p>
    <div class="registration__block">
      <input v-model="form.email" placeholder="Email address" type="email" class="registration__input"/>
    </div>
    <div class="registration__block">
      <input v-model="form.password" placeholder="Password" type="password" class="registration__input"/>
    </div>
    <div class="registration__block">
      <button @click="login" class="btn">Sign In</button>
    </div>
    <div class="registration__block">
      <button @click="registration" class="btn__cancel">Create Account</button>
    </div>
  </div>

</template>

<script>
import BaseInput from "@/components/base/BaseInput";
export default {
  components: {BaseInput},
  layout: "auth",
  data: () =>({
    form:{
      email: null,
      password: null
    }
  }),
  methods:{
    async login(){
      await this.$axios.post('api/auth/login',this.form)
      await this.$router.push('/main')
    },
    registration() {
      this.$router.push('/auth/registration')
    }
  }
}
</script>

<style lang="scss" scoped>
.registration{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 20px;
  &__block{
    margin-bottom: 15px;
  }
  &__input{
    border-radius: 8px;
    padding: 10px;
    width: 335px;
  }
}
.btn{
  background: #387780;
  color: #FFFFFF;
  width: 355px;
  display: flex;
  border-radius: 8px;
  padding: 10px 20px;
  justify-content: center;
  font-family: 'Helvetica Now Display';
  font-style: normal;
  font-weight: 700;
  font-size: 16px;
  line-height: 24px;
  &__cancel{
    background: #FFFFFF;
    padding: 10px 20px;
    width: 355px;
    display: flex;
    justify-content: center;
    border-radius: 8px;
  }
}
</style>
