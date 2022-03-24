<template>
  <main>
    <div class="container py-5">
      <div class="row justify-content-center row-cols-2 row-cols-sm-3 row-cols-md-4 row-cols-lg-6">
        <div v-if="arrCards == null">Loading Data</div>
        <CardDisco v-for="card in arrCards" :key="card.id" :card-data="card" />
      </div>
    </div>

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
      });
  },
};
</script>

<style scoped lang="scss">
  main {
    background-color: rgb(30,45,59);
  }

</style>
