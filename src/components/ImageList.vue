<template>
  <v-container>
    <v-row>
      <v-col v-bind:key="item.char_id" v-for="item in items" sm="4" cols="12">
        <v-card class="ma-5" max-width="600">
          <img class="ma-2" height="300" width="300" :src="item.img" alt />
          <v-card-title>{{ item.nickname }}</v-card-title>
          <v-card-text
            >Name: {{ item.name }}
            <br />
            status: {{ item.status }}
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "ImageList",
  props: ["items"],
};
</script>