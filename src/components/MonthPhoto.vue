<template>
  <div v-if="monthPhoto.media_type ==='image'">
    <h3>{{monthPhoto.date}}</h3>
    <p>{{monthPhoto.title}}</p>
    <img class='photo' v-bind:src='monthPhoto.url'/>
    <button @click="$emit('view-photo', monthPhoto.date)">View</button>
  </div>
  <div v-else>
    <h3>{{monthPhoto.date}}</h3>
    <p>{{monthPhoto.title}}</p>
    <iframe id="ytplayer" type="text/html" width="200" height="150" :src="monthPhoto.url" frameborder="0"></iframe>
    <button @click="$emit('view-photo', monthPhoto.date)">View</button>
  </div>
</template>

<script>
export default {
  name: 'MonthPhoto',
  props: ['monthPhoto']
}
</script>

<style scoped>
  h3 {
    font-size: 18px;
    margin: 2px 2px;
  }
  p {
    margin: 5px 5px;
    font-size: 14px;
    height: 29px;
    text-align: center;
    padding: 0px;
  }
  button {
    margin: 5px 5px;
  }
  .photo {
    height: 150px;
    width: 200px;
    margin-top: 5px;
  }
  #ytplayer{
    margin-top: 5px;
  }
  button {
  background-color: orange;
  height: 30px;
  width: 90px;
  border: 2px solid #65727F;
  border-radius: 20px;
  margin: 2px 0 9px 0;
  font-size: 12px;
  font-weight: bold;
  }
</style>