<template>
  <form class="d-flex justify-content-end align-items-center" action="">
    <label for="select-genre">
      seleziona il genere
      <select v-model="genre" name="select-genre" id="select-genre"
      @change="$emit('genre-selected', genre)">
        <option value="">All</option>
        <option v-for="card in filterGenres()"
        :key="card"
        :value="card">
        {{ card }}
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
    filterGenres() {
      return [...new Set(this.cardsData.map((element) => element.genre))];
    },
  },
};
</script>

<style>

</style>
