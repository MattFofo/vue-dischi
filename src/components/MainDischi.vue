<template>
  <main class="bg-primary">
    <div class="container py-5">
      <InputSelectGenre @genre-selected="(genre) => filterByGenre(genre)" :cards-data="arrCards"
      v-model="genre" />
      <div class="row justify-content-center row-cols-2 row-cols-sm-3 row-cols-md-4 row-cols-lg-6">
        <div v-if="arrCards == null" class="text-center">I'm taking the Data, please wait</div>
        <CardDisco v-model="arrCards" v-for="card in arrCardsFiltered"
        :key="card.title" :card-data="card" />
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
      arrCards: [],
      arrCardsFiltered: [],
    };
  },
  methods: {
    filterByGenre(genre) {
      this.genre = genre;
      this.arrCardsFiltered = this.arrCards.filter((objCard) => objCard.genre.includes(genre));
    },
  },
  created() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((response) => {
        this.arrCards = response.data.response;
        this.arrCardsFiltered = this.arrCards;
      })
      .catch(() => {
        console.log('error');
      });
  },
};
</script>

<style scoped lang="scss">

</style>
