<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div class="editor-wrapper" style="display: inline-flex; max-width: 100%; heigh: 500px">
      <ckeditor :editor="editor" v-model="message" :config="editorConfig"></ckeditor>
    </div>
    <div class="btn-div">
      <button class="btn-ok" type="button" @click="transform(message)">
        <span class="reset-color">Prikitiw</span>
      </button>
    </div>
    <div class="result-wrapper" style="width: 500px; display: inline-flex">
      <p v-html="resText" style="text-align: left">{{ resText }}</p>
    </div>
  </div>
</template>

<script>
import ClassicEditor from "@ckeditor/ckeditor5-build-classic";

export default {
  name: "MinyiComponent",
  props: {
    msg: String
  },
  data: () => {
    return {
      resText: "",
      editor: ClassicEditor,
      editorData: "<p>Rich-text editor content.</p>",
      editorConfig: {
        // The configuration of the rich-text editor.
      }
    };
  },
  model: {
    message: ""
  },
  methods: {
    transform: function(message) {
      this.resText = message.replace(/[aiueo]/g, "i");
      this.resText = this.resText.replace(/[AIUEO]/g, "I");
    }
  }
};
</script>

<style>
.ck.ck-editor__main > .ck-editor__editable {
  height: 300px;
}

@media (max-width: 767px) {
  .ck.ck-editor {
    max-width: 100vw;
  }
}
</style>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.result-text {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-size: 27px;
  font-weight: bold;
  color: #2c3e50;
}
.btn-div {
  height: 25px;
  margin: 40px 20px;
}
.btn-ok {
  background-color: #4caf50;
  min-width: 100px;
  min-height: 50px;
  border: none;
  border-radius: 2px;
  color: white;
  padding: 5px 10px;
  text-align: center;
  text-decoration: none;
  font-size: 16px;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

.result-text {
  min-width: 100px;
  min-height: 300px;
  padding: 20px;
  align-items: center;
}

.btn-submit {
  min-width: 100px;
  max-width: 100%;
  height: 200px;
}

@media (max-width: 767px) {
  .editor-wrapper {
    max-width: 100vw;
    overflow-x: scroll;
  }

  .result-wrapper {
    max-width: 100vw !important;
  }
}
</style>
