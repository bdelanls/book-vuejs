<template>
  <div id="content">
    <h2>Book</h2>
    <h1>Bertrand Delanlssays</h1>
    <main>
      <PortFolio />
    </main>
  </div>
</template>

<script>
import PortFolio from "./components/PortFolio.vue";

export default {
  name: "App",
  components: {
    PortFolio,
  },
  data() {
    return {};
  },
};
</script>

<style></style>
