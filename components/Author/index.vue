<template>
  <div class="container">
    <NuxtLink :to="`/blog/author/${author.name}`">
    <img :src="author.image" />
    <div>
      <h4>Author</h4>
      <p>{{ author.name }}</p>
      <p>{{ author.bio }}</p>
    </div>
    </NuxtLink>
  </div>
</template>
<script>
  export default {
    props: {
      author: {
        type: Object,
        required: true
      }
    }
  }
</script>
<style scoped>
    .container{
        padding:1rem;
        border:1px solid black;
        width:20%;
    }
</style>