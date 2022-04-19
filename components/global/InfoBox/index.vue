<template>
  <div class="blue">
    <p><slot name="info-box">default</slot></p>
  </div>
</template>
<style scoped>
    .blue{
        background:lightblue;
        color:red;
        font-size:2rem;
        font-weight:600;
    }
</style>