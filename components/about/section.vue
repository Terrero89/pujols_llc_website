<script setup lang="ts">
</script>

<template>
  <div>
    <section id="about-section">
      <h1 data-aos="fade-up">About Us</h1>
      <div class="about-container">
        <div class="about-img"></div>
        <div class="about-text">
          <h1>Pujols LLC, Built to Last.</h1>
          <p>
            At Pujols LLC, construction isn't just a job, it's a family tradition. We are [Brother 1 Name] and [Brother 2 Name], two brothers who have spent years honing our skills in the construction industry. Growing up, we learned the value of hard work and dedication from our family, and that same spirit flows through every project we undertake.
          </p>
          <p>
            We founded Pujols LLC with a simple vision: to build exceptional structures that stand the test of time, while fostering a collaborative and trustworthy relationship with our clients. We believe in open communication, transparency, and exceeding expectations. Whether it's a home renovation or a commercial build, we bring the same commitment to quality and craftsmanship to every project.
          </p>
          <p>
            Choose Pujols LLC, and you're not just choosing a construction company, you're choosing a team built on family values and a dedication to excellence. We'll work tirelessly to turn your vision into a reality, a space that reflects your needs and endures for generations to come.
          </p>
        </div>
      </div>
    </section>
  </div>
</template>

<style scoped>
#about-section {
  background-color: #e2e2e2; /* Light gray background */
  margin: 2rem auto;
  padding: 2rem 0; /* Add top and bottom padding */
}

#about-section h1 {
  font-size: 2rem;
  text-align: center;
  margin-bottom: 1rem; /* Add some space after heading */
}

.about-container {

  padding: 1rem;
  display: flex;
  flex-wrap: wrap; /* Allow elements to wrap on smaller screens */
  max-width: 65rem;
  margin: 1rem auto;
}

.about-container .about-img {
  /* background-color: black; */
  flex: 1 1 5rem; /* Image takes up half the width on larger screens */
  background: url("https://images.squarespace-cdn.com/content/v1/5f9af4a881d95f6540043c88/1635607196471-OITL54605J0ATMRMZ9I1/tempImageBANFKy.gif");
  background-size: cover;
  background-position:center;
  background-repeat:no-repeat;
  min-height: 250px; /* Set minimum height for image */
}

.about-text {
  flex: 1 1 10rem;  /* Text takes up half the width on larger screens */

  padding: 2rem;
  color: #333; /* Dark gray text color */
  line-height: 1.5rem; /* Improve readability */

}

/* Media Queries for Smaller Screens */
@media (max-width: 768px) {
  .about-container {
    flex-direction: column; /* Stack elements vertically */
  }
  .about-img,
  .about-text {
    flex: 100%; /* Take full width on small screens */
  }
}
</style>
