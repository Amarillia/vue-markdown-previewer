<template>
  <div id="previewResult">
    <h2>Preview</h2>
    <br />
    <div id="preview">{{transformedText}}</div>
  </div>
</template>

<script>
import marked from "marked";

export default {};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only 
https://vuejs.org/v2/guide/reactivity.html#Declaring-Reactive-Properties
-->
<style scoped>
#preview {
  overflow: hidden;
  overflow-wrap: break-word;
  resize: none;
  height: 500px;
  border: 1px solid #6d8c3e;
  background: #6d8c3e;
  border-radius: 10px;
  width: 300px;
  padding: 15px;
}
h2 {
  text-align: center;
}
</style>
