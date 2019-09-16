<template>
  <div>
    <h2>{{monthPhoto.date}}</h2>
    <p>{{monthPhoto.title}}</p>
    <img class='photo' v-bind:src='monthPhoto.hdurl'/>
  </div>
</template>

<script>
export default {
  name: 'MonthPhoto',
  props: ['monthPhoto']
}
</script>

<style scoped>
  .photo {
    height: 200px;
    width: 200px;
  }
</style>