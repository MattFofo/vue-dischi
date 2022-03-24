<template>
  <div class="card-disco">
    <img :src="cardData.poster" :alt="cardData.title">
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

<style>

</style>
