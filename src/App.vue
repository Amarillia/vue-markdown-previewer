<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <appMainHeader msg="Markdown Live Previewer" />
    <div id="main">
      <codeToTransform />
      <AppPreview />
    </div>
  </div>
</template>

<script>
import appMainHeader from "./components/appMainHeader.vue";
import codeToTransform from "./components/AppForm.vue";
import AppPreview from "./components/AppPreview.vue";

export default {
  name: "app",
  components: {
    appMainHeader,
    codeToTransform,
    AppPreview
  },
  mounted() {
    let recaptchaScript = document.createElement("script");
    recaptchaScript.setAttribute(
      "src",
      "https://cdn.freecodecamp.org/testable-projects-fcc/v1/bundle.js"
    );
    document.head.appendChild(recaptchaScript);
    let markdownScriptLib = document.createElement("script");
    markdownScriptLib.setAttribute(
      "src",
      "https://cdnjs.cloudflare.com/ajax/libs/marked/0.4.0/marked.js"
    );
    document.head.appendChild(markdownScriptLib);
  }
};
</script>

<style>
* {
  background-color: rgb(152, 205, 252);
}

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
}

body {
  margin: 0 auto;
  max-width: 80%;
}

#main {
  display: flex;
  justify-content: space-evenly;
}
</style>
