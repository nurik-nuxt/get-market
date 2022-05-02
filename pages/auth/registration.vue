<template>
  <div class="registration">
    <p>Create Your Account</p>
    <div class="registration__block">
      <input v-model="form.first_name" placeholder="First name" class="registration__input"/>
    </div>
    <div class="registration__block">
      <input v-model="form.last_name" placeholder="Last name" class="registration__input"/>
    </div>
    <div class="registration__block">
      <input v-model="form.email" placeholder="Email address" type="email" class="registration__input"/>
    </div>
    <div class="registration__block">
      <input v-model="form.password" placeholder="Password" type="password" class="registration__input"/>
    </div>
    <div class="registration__block">
      <input v-model="form.password_confirmation" placeholder="Repeat Password" type="password" class="registration__input"/>
    </div>
    <div class="registration__block">
      <button @click="registration" class="btn">Create account</button>
    </div>
    <div class="registration__block">
      <button @click="login" class="btn__cancel">Sign In</button>
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
      first_name: null,
      last_name:  null,
      email: null,
      password: null,
      password_confirmation: null
    }
  }),
  methods:{
    async registration(){
      await this.$axios.post('api/auth/register',this.form)
      await this.$router.push('/auth/login')
    },
    login(){
      this.$router.push('/auth/login')
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
  padding: 10px 15px;
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
