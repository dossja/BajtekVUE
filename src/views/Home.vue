<template>
  <div class="home">
    <HelloWorld msg="Welcome to Your Home Page" />
    <div id="data1">Another text</div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "Home",
  components: {
    HelloWorld,
  },
};
</script>

<style>
#data1 {
  background: #212121;
}
</style>
