<template>
  <div id="app">
    <input type="text" @keyup="triggerSearch" v-model="searchInput">
    <b-table
      :data="displayedData"
      :columns="columns"
      :striped="true"
      custom-row-key="id"
      class="groups-table"
      :default-sort="['id', 'desc']"
      hoverable
    ></b-table>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import HelloWorld from './components/HelloWorld.vue';

export default Vue.extend({
  name: 'App',
  data() {
    return {
      searchInput: "",
      columns: [
        {
          field: "name_name",
          label: "name_name",
        },
        {
          field: "group_name",
          label: "group_name",
        },
        {
          field: "random",
          label: "random",
        },
      ],
      tableData: [
        {
          id: 18,
          data_owner: 28,
          group_name: "blue ocean",
          nickname: "",
          is_active: true,
          client_id: 2222222,
          testi_id: 2222222,
          name_name: "test name",
          order_id: 1111111,
          random: "deg",
          point_ids: [22222222],
          random_ids: [2222221, 2222222, 2222222],
          name_id: null,
        },
        {
          id: 8,
          data_owner: 28,
          group_name: "Test Group!",
          nickname: "",
          is_active: true,
          client_id: 2222222,
          testi_id: 2222222,
          name_name: "dave scott",
          order_id: 1111111,
          random: "abc",
          point_ids: [22222222],
          random_ids: [2222221, 2222222, 2222222],
          name_id: null,
        },
        {
          id: 118,
          data_owner: 28,
          group_name: "Hello name",
          nickname: "",
          is_active: true,
          client_id: 2222222,
          testi_id: 2222222,
          name_name: "Testi",
          order_id: 1111111,
          random: "sts",
          point_ids: [22222222],
          random_ids: [2222221, 2222222, 2222222],
          name_id: null,
        },
        {
          id: 19,
          data_owner: 28,
          group_name: "bye world",
          nickname: "",
          is_active: true,
          client_id: 2222222,
          testi_id: 2222222,
          name_name: "new name",
          order_id: 1111111,
          random: "rth",
          point_ids: [22222222],
          random_ids: [2222221, 2222222, 2222222],
          name_id: null,
        },
        {
          id: 15,
          data_owner: 28,
          group_name: "milkyway",
          nickname: "",
          is_active: true,
          client_id: 2222222,
          testi_id: 2222222,
          name_name: "mike name",
          order_id: 1111111,
          random: "kih",
          point_ids: [22222222],
          random_ids: [2222221, 2222222, 2222222],
          name_id: null,
        },
      ],
      displayedData: [],
    };
  },
  methods: {
    triggerSearch() {
      this.displayedData = this.tableData;
      const searchString = this.searchInput.toLowerCase();
      const filteredData = this.tableData.filter(
        (entry) =>
          entry.name_name.toLowerCase().includes(searchString) ||
          entry.random.toLowerCase().includes(searchString) ||
          entry.group_name.toLowerCase().includes(searchString),
      );
      this.displayedData = filteredData;
    },
  },
  created() {
    this.triggerSearch();
  },
  components: {
    HelloWorld,
  },
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
