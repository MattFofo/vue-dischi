<template>
  <header>
    <div class="container-fluid">
      <div class="row row-cols-2 justify-space-between">
        <i class="fa-brands fa-spotify py-3"></i>
      </div>
    </div>
  </header>
</template>

<script>

export default {
  name: 'HeaderDischi',
};

</script>

<style scoped lang="scss">
header {
  background-color: rgb(46,58,70);
  .fa-spotify {
    font-size: 3rem;
    color: #1ED760;
  }
}

</style>
