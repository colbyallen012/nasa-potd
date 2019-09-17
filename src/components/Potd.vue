<template>
  <div id='photoContainer'>
    <img class='potd' v-bind:src='photo.url'/>
    <div className='infoContainer'>
      <h2>{{photo.title}}</h2>
      <h3>Date: {{photo.date}}</h3>
      <p>{{photo.explanation}}</p>
    </div>
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
    height: 100%;
    background-color: rgba(101, 114, 127, .15);
  }
  #infoContainer {
    padding: 0 10px 0 10px;
    height: 100%;
  }
  p {
    font-weight: bold;
    padding: 10px;
    margin: auto;
    width: 75%;
  }
  .potd {
    width: 750px;
    height: 475px;
  }

  h3, h4 {
    margin: 5px 5px,
  }
</style>