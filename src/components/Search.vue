<template>
  <v-container>
    <v-row>
      <v-col>
        <v-btn
          class="mx-2"
          fab
          dark
          color="blue lighten-34"
          @click="searchItem"
        >
          <v-icon>mdi-magnify</v-icon>
        </v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>
<script>
import axios from "axios";

export default {
  name: "Search",
  data() {
    return {
      search: [],
      word: "",
    };
  },
  methods: {
    searchItem() {
      axios
        .get("https://breakingbadapi.com/api/characters")
        .then((response) => {
          this.search = response.data;
          this.$emit("searchResult", response.data);
        })
        .catch((err) => {
          console.log(err);
        });
    },
  },
};
</script>