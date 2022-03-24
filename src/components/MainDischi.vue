<template>
  <main>
    <CardDisco card-poster= "" card-data="" card-title="" card-author="" card-year="" />
  </main>
</template>

<script>
import axios from 'axios';
import CardDisco from './CardDisco.vue';

export default {
  name: 'MainDischi',
  components: {
    CardDisco,
  },
  created() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((response) => {
        console.log(response.data.response);
      });
  },
};
</script>

<style>

</style>
