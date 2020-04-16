<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <myeditor />
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import myeditor from "./components/myeditor.vue";
export default {
  name: "App",
  components: {
    myeditor
  }
};
</script>
