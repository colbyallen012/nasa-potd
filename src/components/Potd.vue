<template>
  <div>
    <img class='potd' v-bind:src='photo.hdurl'/>
    <p>{{photo.explanation}}</p>
  </div>
</template>

<script>

export default {
  name: 'Potd',
  props: {
    photo: String
  }
}
</script>

<style scoped>
  p {
    font-weight: bold;
  }

  .potd {
    width: 100%;
    height: 25%;
  }
</style>