<template>
  <div class="card-disco col-6 col-md-4 col-lg-2 m-2">
    <img class="img-fluid" :src="cardData.poster" :alt="cardData.title">
    <h3>{{ cardData.title }}</h3>
    <h4>{{ cardData.author }}</h4>
    <h4>{{ cardData.year }}</h4>
  </div>
</template>

<script>
export default {
  name: 'CardDisco',
  props: {
    cardData: Object,
  },
};
</script>

<style scoped lang="scss">
  .card-disco{
    background-color: rgb(46,58,70);
    h3 {
      color: white;
    }
    h4 {
      color: rgb(110,122,124);
    }
  }

</style>
