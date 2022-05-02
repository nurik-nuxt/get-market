<template>
  <div>
    <Header/>
    <nuxt/>
    <Footer/>
  </div>
</template>
<script>
import Header from "~/components/common/Header/Header";
import Footer from "@/components/common/Footer/Footer";
export default {
  components: {Footer, Header}
}
</script>
