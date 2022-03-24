<template>
  <main>
    <div v-if="arrCards == null">Loading Data</div>
    <CardDisco v-for="card in arrCards" :key="card.id" :card-data="card" />
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
  data() {
    return {
      arrCards: null,
    };
  },
  created() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((response) => {
        this.arrCards = response.data.response;
        console.log(this.arrCards);
      });
    // console.log(this.arrCards);
  },
};
</script>

<style>

</style>
