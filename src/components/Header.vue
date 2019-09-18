<template>
  <div id=head>
    <img class='nasa' src="../assets/nasa.png"/>
    <h1>Astronomy Photo of the Day</h1>
  </div>
</template>

<script>
export default {
  name: 'Header',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#head {
  display: flex;
  flex-direction: row;
  justify-content: center;
}

.nasa {
  margin-top: 2px;
  height: 60px;
  width: 70px;
}
h1 {
  margin: 10px 0 10px 0;
  color: orange;
  text-shadow: #65727F;
}
</style>
