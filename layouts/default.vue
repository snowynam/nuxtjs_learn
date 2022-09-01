<template>
  <div>
    <header>
      <h1>{{$route.name}} 페이지</h1>
      <nuxtLink to="/">홈페이지</nuxtLink>
      <nuxtLink to="/main">메인 페이지</nuxtLink>
      <nuxtLink to="/product">상품 페이지</nuxtLink>
      <!-- <nuxtLink></nuxtLink> == <router-link></router-link> -->
    </header>
    <Nuxt />
    <!-- <Nuxt /> == <router-view></router-view> -->
  </div>
</template>

<script>
export default {
  // created(){
  //   console.log(this.$route)
  // },
}
</script>

<style>

</style>