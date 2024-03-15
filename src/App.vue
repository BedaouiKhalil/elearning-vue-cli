<template>
  <Header />

  <div class="container p-md-3">
    <ListCourse />
  </div>

  <Footer />
</template>

<script>
import ListCourse from "./components/ListCourse.vue";
import Header from "./components/Header.vue";
import AddCourse from "./components/AddCourse.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "App",
  components: {
    Header,
    AddCourse,
    Footer,
    ListCourse,
  },

  data() {},
  methods: {},
};
</script>

<style scoped></style>
