<template>
  <form class="d-flex justify-content-end align-items-center" action="">
    <label for="select-genre">
      seleziona il genere
      <select v-model="genre" name="select-genre" id="select-genre">
        <option v-for="card in cardsData"
        :key="card.poster"
        :value="card.genre" @change="$emit('genre-selected', genre)">
        {{ card.genre }}
        </option>
      </select>
    </label>
  </form>
</template>

<script>
export default {
  name: 'InputSelectGenre',
  props: {
    cardsData: Array,
  },
  data() {
    return {
      genre: '',
    };
  },
  methods: {
    getArrGenres() {
      this.cardsData.forEach((element) => { this.arrGenres.push(element.genre); });
    },
  },
};
</script>

<style>

</style>
