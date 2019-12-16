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
    font-size: 15px;
    padding: 10px;
    margin: 5px auto;
    width: 75%;
  }
  .potd {
    width: 675px;
    height: 425px;
  }

  h2 {
    margin-top: 5px;
  }

  h3, h4 {
    margin: 5px 0 5px 0;
  }

  #video-responsive{
    height: 400px;
    width: 900px;
    margin: 75px 40px 0px 75px;
  }

  button {
    background-color: orange;
    height: 30px;
    width: 150px;
    border: 2px solid #65727F;
    border-radius: 20px;
    margin: 9px 0 9px 0;
    font-size: 12px;
    font-weight: bold;
  }

@media (max-width: 414px) {
    #photoContainer {
    display: flex;
    flex-direction: column;
    width: 100%;
    height: 100%;
  }

    .potd {
    width: 95%;
    height: 225px;
    margin: auto;
  }

    p {
    font-weight: bold;
    font-size: 15px;
    padding: 5px;
    margin: 5px auto;
    width: 92%;
  }
}

@media (max-width: 1064px) {
  #photoContainer {
    display: flex;
    flex-direction: column;
    width: 100%;
    height: 100%;
    background-color: rgba(101, 114, 127, .15);
  }

  .potd {
    width: 85%;
    height: 325px;
    margin: auto;
  }
}


</style>