<template lang="">
  <form class="my-5" @submit.prevent="newCourse">
    <div class="mb-3">
      <label for="title" class="form-label">Title</label>
      <input type="text" class="form-control" id="title" v-model="title" />
    </div>
    <div class="mb-3">
      <label for="price" class="form-label">Price</label>
      <input type="text" class="form-control" id="price" v-model="price" />
    </div>
    <div class="mb-3">
      <label for="Image">Image url</label>
      <input v-model="image" id="Image" type="text" class="form-control" />
    </div>

    <div class="mb-3">
      <label for="category">Category</label>
      <select v-model="category" id="category" class="form-control">
        <option :value="myCategory.id" v-for="myCategory in categories">
          {{ myCategory.name }}
        </option>
      </select>
    </div>

    <button
      type="submit"
      class="btn w-100"
      style="background-color: #6c61fe; /* Green */ border: none; color: white"
    >
      Add Course
    </button>
  </form>
</template>
<script>
export default {
  data() {
    return {
      title: "",
      image: "",
      price: "",
      category: 2,
      categories: [
        { id: 1, name: "Frontend" },
        { id: 2, name: "Backend" },
        { id: 3, name: "Mobile" },
      ],
    };
  },
  methods: {
    newCourse() {
      let title = this.title;
      let image = this.image;
      let price = this.price;

      if (title == "" || image == "" || isNaN(price) || price == "") {
        alert("value is invalid");
        return;
      }

      const course = {
        title,
        image,
        price,
        category: this.categories.find(
          (category) => category.id == this.category
        ).name,
      };

      this.$emit("add", course);

      this.title = "";
      this.image = "";
      this.price = "";
    },
  },
};
</script>
<style lang=""></style>
