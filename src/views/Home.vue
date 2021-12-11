<template>
  <v-container fluid>
    <v-row>
      <v-col>
        <div class="buttons-container">
          <v-btn small elevation="0">Image</v-btn>
          <v-btn small elevation="0">Video</v-btn>
          <v-btn small elevation="0">Description</v-btn>
          <v-btn small elevation="0">Quote</v-btn>
          <v-btn small elevation="0">Footnote</v-btn>
          <v-btn small elevation="0">Link</v-btn>
          <v-btn small elevation="0">Button</v-btn>
          <v-btn small elevation="0">File</v-btn>
          <v-btn small elevation="0">2 Columns</v-btn>
          <v-btn small elevation="0">Table</v-btn>
          <v-btn small elevation="0">Table row</v-btn>
        </div>

        <v-textarea
          name="input-7-1"
          filled
          outlined
          auto-grow
          value="The Woodman set to work at once, and so sharp was his axe that the tree was soon chopped nearly through."
        ></v-textarea>
      </v-col>
      <v-col>
        <v-textarea
          name="input-7-1"
          filled
          outlined
          auto-grow
          disabled
        ></v-textarea>
      </v-col>
    </v-row>
  </v-container>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "Home",

  components: {},
});
</script>

<style scoped>
.buttons-container {
  display: flex;
  justify-content: space-between;
}
</style>
