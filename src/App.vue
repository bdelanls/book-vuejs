<template>
  <div id="content">
    <h2>Book</h2>
    <header>
      <h1>Bertrand Delanlssays</h1>
    </header>
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

<style>
body {
  background: #303030;
  display: flex;
  justify-content: center;
}
#content {
  max-width: 960px;
  margin: 0 auto;
  display: block;
  position: relative;
}
</style>
