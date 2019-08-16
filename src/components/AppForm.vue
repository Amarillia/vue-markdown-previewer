<template>
  <div class="codeToTransform">
    <form action method="get">
      <h2>Add your code:</h2>
      <br />
      <textarea
        id="editor"
        rows="5"
        cols="50"
        name="description"
        :value="inputValue"
        @input="markdownText"
        placeholder="Your code comes here..."
      ></textarea>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      inputValue: "<p>Hello</p>"
    };
  },
  methods: {
    markdownText(e) {
      this.inputValue = e.target.value;
    },
    computed: {
      transformedText() {
        var tText = document.getElementById("preview");
        tText.innerHTML = marked(this.inputValue, { sanitize: true });
      }
    }
  }
};
</script>

<!-- https://codepen.io/anuragasaurus/pen/ybjjdN -->
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
textarea {
  overflow: hidden;
  overflow-wrap: break-word;
  width: 300px;
  resize: none;
  height: 500px;
  border: 1px solid #f2b705;
  background: #f2b705;
  border-radius: 10px;
}

h2 {
  text-align: center;
}

#editor {
  padding: 15px;
}
</style>
