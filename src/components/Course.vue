<template lang="">
  <div class="card mb-4" style="border: solid 1px #6c61fe">
    <div class="row g-0">
      <div class="col-md-2">
        <img
          :src="course.image"
          class="img-fluid rounded-start h-100"
          :alt="course.title"
        />
      </div>
      <div class="col-md-10">
        <div class="card-body">
          <h5 class="card-title" style="color: #6c61fe">{{ course.title }}</h5>
          <p class="card-text">
            This is a wider card with supporting text below as a natural lead-in
            to additional content. This content is a little bit longer.
          </p>
          <hr style="color: #6c61fe" />
          <div class="row">
            <div class="col-10">
              <p class="card-text">
                <small class="text-body-secondary">{{ course.category }}</small>
              </p>
            </div>

            <div class="col-2">
              <p class="text-end fw-bold" style="color: #6c61fe">
                {{ course.price }} USD
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["course"],
};
</script>
<style lang=""></style>
