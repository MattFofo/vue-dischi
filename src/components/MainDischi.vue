<template>
  <main class="bg-primary">
    <div class="container py-5">
      <InputSelectGenre @genre-selected="filterByGenre()" :cards-data="arrCards" />
      <div class="row justify-content-center row-cols-2 row-cols-sm-3 row-cols-md-4 row-cols-lg-6">
        <div v-if="arrCards == null" class="text-center">Missing Data</div>
        <CardDisco v-model="genre" v-for="card in arrCards"
        :key="card.id" :card-data="card" />
      </div>
    </div>

  </main>
</template>

<script>
import axios from 'axios';
import CardDisco from './CardDisco.vue';
import InputSelectGenre from './InputSelectGenre.vue';

export default {
  name: 'MainDischi',
  components: {
    CardDisco,
    InputSelectGenre,
  },
  data() {
    return {
      genre: '',
      arrCards: null,
    };
  },
  methods: {
    filterByGenre() {
      this.arrCards = this.arrCards.filter((objCard) => objCard.genre.includes('Jazz'));
    },
  },
  created() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((response) => {
        this.arrCards = response.data.response;
      })
      .catch(() => {
        console.log('error');
      });
  },
};
</script>

<style scoped lang="scss">

</style>
