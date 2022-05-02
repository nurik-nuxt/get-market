<script>
export default {
  middleware({store, redirect}){
    return redirect("/auth/login")
  }
}
</script>
