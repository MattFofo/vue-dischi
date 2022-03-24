<template>
  <div class="card-disco bg-secondary m-3 p-4">
    <img class="img-fluid" :src="cardData.poster" :alt="cardData.title">
    <h3 class="text-center py-2">{{ cardData.title }}</h3>
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
    h3 {
      color: white;
      line-height: 1;
    }
    h4 {
      color: rgb(110,122,124);
      line-height: .8;
      font-size: 1.1rem;
    }
  }

</style>
