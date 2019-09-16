<template>
  <div id='photoContainer'>
    <img class='potd' v-bind:src='photo.hdurl'/>
      <h2>{{photo.title}}</h2>
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
  #photoContainer {
    display: flex;
    flex-direction: row;
    width: 100%;
  }
  p {
    font-weight: bold;
  }
  .potd {
    width: 750px;
    height: 530px;
  }
</style>