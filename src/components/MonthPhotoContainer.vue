<template>
  <div id='monthContainer'>
    <div id='dayContainer' v-bind:key='monthPhoto.date' v-for='monthPhoto in monthPhotos'>
      <MonthPhoto v-bind:monthPhoto='monthPhoto' v-on:view-photo="$emit('view-photo', monthPhoto.date)"/>
    </div>
  </div>
</template>

<script>
import MonthPhoto from './MonthPhoto.vue'

export default {
  name: 'MonthPhotoContainer',
  components: {
    MonthPhoto
  },
  props: ['monthPhotos']
}
</script>

<style scoped>
  #monthContainer {
    display: flex;
    flex-direction: row;
    overflow: auto;
  }

  #dayContainer {
    margin: 5px;
    background-color: rgba(101, 114, 127, .15);
  }
</style>