<template>
  <div class="block2">
      <h1>Results are {{ score }} </h1>
  </div>

</template>

<script>
export default {
    props: ['score']

}
</script>

<style>

.block2 {
    width: 800px;
    border-radius: 20px;
    background: blue;
    padding: 10px 0;
    margin: 40px auto;
}

</style>