<script setup lang="ts">
</script>

<template>
  <div>
    <section id="service-section">
      <h1 data-aos="fade-up">Our Services</h1>
      <div class="service-container">
      <div>hello</div>
        <div>hello</div>
        <div>hello</div>
        <div>hello</div>

      </div>
    </section>
  </div>
</template>

<style scoped>
#service-section {
  background-color: #e2e2e2; /* Light gray background */
  margin: 2rem auto;
  padding: 2rem 0; /* Add top and bottom padding */
}

#service-section h1 {
  font-size: 2rem;
  text-align: center;
  margin-bottom: 1rem; /* Add some space after heading */
}

.service-container {

  padding: 1rem;
  display: flex;
  flex-wrap: wrap; /* Allow elements to wrap on smaller screens */
  max-width: 65rem;
  margin: 1rem auto;
}

.service-container .service-img {
  /* background-color: black; */
  flex: 1 1 10rem; /* Image takes up half the width on larger screens */
  background: url("https://images.squarespace-cdn.com/content/v1/5f9af4a881d95f6540043c88/1635607196471-OITL54605J0ATMRMZ9I1/tempImageBANFKy.gif");
  background-size: cover;
  background-position:center;
  background-repeat:no-repeat;
  min-height: 250px; /* Set minimum height for image */
}

.service-text {
  flex: 1 1 10rem;  /* Text takes up half the width on larger screens */

  padding: 1rem;
  color: #333; /* Dark gray text color */
  line-height: 1.5rem; /* Improve readability */

}

/* Media Queries for Smaller Screens */
@media (max-width: 768px) {
  .about-container {
    flex-direction: column; /* Stack elements vertically */
  }
  .service-img,
  .service-text {
    flex: 100%; /* Take full width on small screens */
  }
}
</style>
