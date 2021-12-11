<template>
  <v-container fluid>
    <v-row>
      <v-col class="max-width-textarea">
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
          class="markdown-editor max-width-textarea-editor"
          :value="input"
          @input="update"
        ></v-textarea>
      </v-col>
      <div class="vertical-line" />
      <v-col>
        <div
          class="max-width-textarea-output markdown-output"
          v-html="compiledMarkdown"
        ></div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script lang="ts">
import Vue from "vue";
import marked from "marked";
import _ from "lodash";
import decodeHtml from "decode-html";

export default Vue.extend({
  name: "Home",

  components: {},
  data() {
    return {
      input: "# hello",
    };
  },
  computed: {
    compiledMarkdown: function () {
      const result = marked(this.input, { sanitize: true });
      console.log(result);
      return decodeHtml(result);
    },
  },
  methods: {
    update: _.debounce(function (e) {
      this.input = e;
    }, 300),
  },
});
</script>

<style scoped>
.buttons-container {
  display: flex;
  justify-content: space-between;
}

.max-width-textarea-editor {
  max-width: 960px;
}

.max-width-textarea-output {
  max-width: 900px;
}

.markdown-editor {
  white-space: normal !important;
  max-width: 980px;
}
.markdown-output {
  text-align: left !important;
  margin-top: 2rem;
}
.vertical-line {
  height: 100vh;
  width: 2px;
  margin: 0;
  margin-right: 2rem;
  padding: 0;
  background-color: black;
}
</style>
