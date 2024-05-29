
<script setup>
// Define props for title and subtitle (optional)
const props = defineProps({
  title: String,
  subtitle: String,
  text: String,
});
</script>



<template>
  <section class="hero">

    <div class="hero-content">

      <h1>{{ props.title }}</h1>
      <h3>{{ props.subtitle }}</h3>
      <p>{{props.text}}</p>
  
      <button class="btn">Our Gallery</button>
    </div>
    
  </section>
</template>



<style scoped>
.hero {
  height: calc(100vh - 4rem); /* Adjust based on navbar height */
  background: linear-gradient(rgb(0, 0, 0, .8),transparent),url("https://edqubur2ys5.exactdn.com/wp-content/uploads/2023/11/Rox-Roofing-Our-Services-Residential-Roofing-1.jpg?strip=all&lossy=1&ssl=1");
  background-size: cover;
  filter:contrast(80%);
  background-position: center;
  display: flex;
  justify-content: center;
  align-items: center;
  color: #fff;
  max-height: 70vh;

}

.hero-content {
  max-width: 65rem;
  text-align: center;
  padding:2rem  1rem;
  /* border:solid rgb(180, 180, 180) 1px; */
  background-color:rgb(190, 190, 190, 0.35);

}

/* Responsive Styles using Media Queries */
@media (max-width: 768px) {
  .hero-content {
    max-width: 100%; /* Content fills entire width on small screens */
    h1{
      font-size: 3rem; /* Adjust heading sizes for smaller screens */
    }
    h3 {
      font-size: 2rem;
    }
    p {
      font-size: 1.2rem;
    }
  }
}

/* Cleaned Up Styles */
.hero-content h1,
.hero-content h3,
.hero-content p {
  margin-bottom: 1rem; /* Apply margin to all headings and paragraph */
}
.hero-content h1{
  font-size: 4rem; 
}

.hero-content h3{
  font-size: 2.6rem; 
  margin:1rem;
}
.hero-content p{
  font-size: 1.4rem;
  margin:1rem;
}

.btn {

padding: 10px 18px;
border:solid white 1px;
border-radius: 8px;
font-size: 1.1rem;
background-color: red;
color:white;
font-weight: bold

}


.btn:hover {
  transition: 0.3s;
  background: #e72e2e;

  text-decoration: none;
}
</style>