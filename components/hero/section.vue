<template>
  <section class="hero">
    <div class="hero-content">
      <h1>{{ props.title }}</h1>
      <p>{{ props.subtitle }}</p>
      <slot />
    </div>
  </section>
</template>

<script setup>
// Define props for title and subtitle (optional)
const props = defineProps({
  title: String,
  subtitle: String
});
</script>

<style scoped>
.hero {
  height: calc(100vh - 4rem); /* Adjust based on navbar height */
  background-image: url("https://media.istockphoto.com/id/1305995602/photo/responsive-floating-responsive-design.jpg?s=2048x2048&w=is&k=20&c=S6uWUdjwkUkWu5zFy1FGb8tSgFzbVlufZytYatTSdnE="); /* Replace with your image */
  background-size: cover;
  background-position: center;
  display: flex;
  justify-content: center;
  align-items: center;
  color: #fff;
}

.hero-content {
  text-align: center;
}

h1 {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

p {
  font-size: 1.2rem;
}
</style>