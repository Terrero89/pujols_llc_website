<template>
  <div
      class="about-img"
      data-aos="fade-zoom-in"
      data-aos-easing="ease-in-back"
      data-aos-offset="250"

  >
    <div class="square">
      <img

          data-aos="fade-up"
          data-aos-delay="350"
          data-aos-offset="250"
          alt="my-avatar"
      />
    </div>
  </div>
</template>


<style scoped>
.about-container .square {
  background:url("https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTaVUNIzfvWXfqtw7xjE6c8XyIZFsp7W6agQO6O9Ci6W8OSjGFkOg365xZAPkTdTBNNcy8&usqp=CAU");

  position: relative;
  margin-top: 0;
  /* border: solid red 1px; */
  width: 100%;
  height: 100%;
  border-radius: 5px;

  margin: 5rem 0 0 0;
}

#about .about-img {
  overflow: hidden;

  margin: 5rem 5rem;
  background-color: rgb(255, 255, 255, 0.4);
  /* border: solid red 1px; */
  width: 32rem;
  height: 32rem;

  /* margin-bottom: 5rem; */
}

#about .about-container .about-img img {
  position: absolute;
  /* border-radius: 0% 0% 50% 50%; */
  object-fit: contain;
  width: 100%;
  bottom: 3rem;
  height: 100%;
  border-radius: 5px;
}

@media only screen and (max-width: 768px) {
  #about .about-img {
    /* border: solid red 1px; */
    margin: 5rem 5rem;
    border-radius: 55%;
    bottom: 4rem;
  }

  #about .about-container .about-img img {
    position: absolute;
    order: 1;
    object-fit: contain;
    width: 100%;
    bottom: 3rem;
    height: 100%;
    border-radius: 5px;

  }
}
</style>