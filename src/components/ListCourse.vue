<template lang="">
  <!--add course-->
  <div class="row" v-if="showForm">
    <div class="col-md-6 mx-auto">
      <AddCourse @add="addCourse($event)" />
    </div>
  </div>
  <!--end add course-->

  <!-- show form -->
  <div class="row mb-4">
    <div class="col-md-6 text-right mt-3">
      <button
        @click="displayForm"
        class="btn btn-sm"
        :class="{ 'color-p': !showForm, 'btn-dark': showForm }"
      >
        {{ showForm ? "Close Form" : "New Course" }}
      </button>
    </div>
  </div>
  <!-- end show form-->

  <h3 style="color: #6c61fe">List of Courses</h3>

  <div v-for="course in courses">
    <Course :course="course" />
  </div>

  <!--alert-->
  <teleport to="#alert" v-if="courseadd">
    <div class="alert alert-success text-center">
      <strong>Course is added successfully !</strong>
    </div>
  </teleport>
</template>

<script>
import AddCourse from "./AddCourse";
import Course from "./Course";
export default {
  components: {
    AddCourse,
    Course,
  },

  data() {
    return {
      showForm: false,
      courseadd: false,
      courses: [
        {
          id: 1,
          title: "Learn ReactJS",
          category: "Frontend",
          price: 35,
          tags: [],
          image: "https://img-c.udemycdn.com/course/240x135/2316454_1f6a_6.jpg",
        },
        {
          id: 2,
          title: "Learn Angular",
          price: 25,
          category: "Frontend",
          tags: [],
          image: "https://img-c.udemycdn.com/course/240x135/756150_c033_2.jpg",
        },
        {
          id: 3,
          title: "Learn Javascript",
          category: "Frontend",
          price: 45,
          tags: [],
          image: "https://img-b.udemycdn.com/course/240x135/3613504_e0e9_5.jpg",
        },
        {
          id: 4,
          title: "Learn Node js",
          category: "Backend",
          price: 65,
          tags: [],
          image: "https://img-c.udemycdn.com/course/240x135/2316454_1f6a_6.jpg",
        },
      ],
    };
  },
  methods: {
    displayForm() {
      this.showForm = !this.showForm;
    },
    addCourse(course) {
      this.courses = [course, ...this.courses];
      this.showForm = false;
      this.courseadd = true;

      setTimeout(() => {
        this.courseadd = false;
      }, 3000);
    },
  },
};
</script>
<style scoped>
.color-p {
  background-color: #6c61fe;
  color: white;
}
</style>
