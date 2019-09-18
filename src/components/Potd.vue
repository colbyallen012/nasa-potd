<template>
  <div v-if="photo.media_type ==='image'" id='photoContainer'>
    <img class='potd' v-bind:src='photo.url'/>
    <div className='infoContainer'>
      <h2>{{photo.title}}</h2>
      <h3>Date: {{photo.date}}</h3>
      <p>{{photo.explanation}}</p>
      <button @click="$emit('home-photo')">View Today's Photo</button>
    </div>
  </div>
  <div v-else id='photoContainer'>
    <div id="video-responsive">
    <iframe id="ytplayer" type="text/html" width="600" height="350"
      :src="photo.url" frameborder="0"></iframe>
    </div>
    <div className='infoContainer'>
      <h2>{{photo.title}}</h2>
      <h3>Date: {{photo.date}}</h3>
      <p>{{photo.explanation}}</p>
      <button @click="$emit('home-photo')">View Today's Photo</button>
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
    font-size: 13px;
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

  #video-responsive{
    height: 400px;
    width: 900px;
    margin: 75px 40px 0px 75px;
  }
</style>