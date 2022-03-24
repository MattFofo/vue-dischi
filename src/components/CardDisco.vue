<template>
  <div class="card-disco m-3">
    <img class="img-fluid" :src="cardData.poster" :alt="cardData.title">
    <h3 class="text-center">{{ cardData.title }}</h3>
    <h4 class="text-center">{{ cardData.author }}</h4>
    <h4 class="text-center">{{ cardData.year }}</h4>
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
