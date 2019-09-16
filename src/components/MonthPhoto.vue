<template>
  <div>
    <h3>{{monthPhoto.date}}</h3>
    <p>{{monthPhoto.title}}</p>
    <img class='photo' v-bind:src='monthPhoto.url'/>
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
  .photo {
    height: 200px;
    width: 200px;
  }
</style>