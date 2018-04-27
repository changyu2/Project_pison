<template>
  <div id="Release">
    <Searchbar></Searchbar>
    <Table></Table>
  </div>
</template>

<style scoped>
#Release {
  width: 80%;
  height: 100%;
  background-color: #e7f3f7;
  float: left;
}
</style>

<script>
import Searchbar from './Searchbar';
import Table from './Table';

export default {
  components: {
    Searchbar,
    Table
  }
};
</script>
