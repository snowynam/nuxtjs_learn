<template>
  <div>
    <h1 v-if="error.statusCode === 404">Page not found</h1>
    <h1 v-else>An error occured</h1>
    <p>페이지를 찾을 수 없습니다.</p>
  </div>
</template>

<script>
export default {
    props: ['error'],
    layout: 'error' // you can set a custom layout for the error page
}
</script>

<style>

</style>