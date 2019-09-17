<template>
  <div v-if="monthPhoto.media_type ==='image'">
    <h3>{{monthPhoto.date}}</h3>
    <p>{{monthPhoto.title}}</p>
    <button @click="$emit('view-photo', monthPhoto.date)">View</button>
    <img class='photo' v-bind:src='monthPhoto.url'/>
  </div>
  <div v-else>
    <h3>{{monthPhoto.date}}</h3>
    <p>{{monthPhoto.title}}</p>
    <button @click="$emit('view-photo', monthPhoto.date)">View</button>
    <video width='200' height='200' controls :src="monthPhoto.url"></video>
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
    margin: 2px 2px;
  }
  p {
    margin: 5px 5px;
    font-size: 12px;
    height: 30px;
    text-align: center;
    padding: 5px;
  }
  button {
    margin: 5px 5px;
  }
  .photo {
    height: 200px;
    width: 200px;
  }
</style>