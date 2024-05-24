<template>
  <div >
    <nav
        class="navbar"
        :class="{ navbarOn: isScrolled, navbarOff: !isScrolled }"
    >
      <a href="#" class="nav-logo">ST</a>
      <ul class="nav-menu" :class="{ active: menuIsVisible }">
        <li class="nav-item" @click="toggleOn"><a href="#about" class="nav-link">About</a>
        </li>
      </ul>
      <div class="hamburger" @click="toggleOn" :class="{ active: menuIsVisible }">
        <span class="bar"></span>
        <span class="bar"></span>
        <span class="bar"></span>
      </div>
    </nav>
  </div>
</template>

<script setup>
import {ref, onMounted, onBeforeUnmount} from 'vue';
// Assuming TheTriangle component path

const menuIsVisible = ref(false);
const isScrolled = ref(false);

const updateScroll = () => {
  if (
      document.body.scrollTop > 50 ||
      document.documentElement.scrollTop > 50
  ) {
    isScrolled.value = true;
  } else {
    isScrolled.value = false;
  }
};

const toggleOn = () => {
  menuIsVisible.value = !menuIsVisible.value;
};

onMounted(() => {
  window.addEventListener('scroll', updateScroll);
  updateScroll(); // Call initially to set state
});

onBeforeUnmount(() => {
  window.removeEventListener('scroll', updateScroll);
});
</script>

<style scoped>
/* Your styles here */
</style>


<style scoped>

.navbar {
  border: solid black 1px;
  height: 4rem;
  position: fixed;
  width: 100%;
  top: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 1.5rem 1.5rem;
  z-index: 3; /* Assuming no header element */

  overflow: hidden;
  /*background-color: rgb(28, 26, 51);*/
}

.navbarOn {
  background-color: #01152e;
  /* backdrop-filter: blur(10px); */
  transition: background 600ms ease-out;
  position: fixed;
  width: 100%;
  top: 0;
  box-shadow: 5px 5px 15px 1px rgba(0, 0, 0, 0.2);
  border-bottom: 1px rgb(44, 44, 44, 0.1) solid;
  padding: 1.5rem 1.5rem;
  z-index: 2;
  overflow: hidden;
}

.navbarOff {
  overflow: hidden;
  position: fixed;
  width: 100%;
  top: 0;
  background-color: none;
  transition: background 600ms ease-in;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }

  to {
    opacity: 1;
  }
}

@keyframes fadeOut {
  from {
    opacity: 1;
  }

  to {
    opacity: 0;
  }
}

/* hover effect starts */
nav .nav-logo,
nav .nav-link {
  position: relative;

  /* color: #71DFE7; */
  color: rgba(44, 43, 44, 0.8);
}

/*underline for links start*/
nav .nav-logo::before {
  content: "";
  display: block;
  height: 1px;
  background: #61DBFB;;
  position: absolute;
  top: 1.2em;
  left: 0;
  right: 0;
  transform: scale(0, 1);
  transition: transform ease-in-out 250ms;
}

nav .nav-link::before {
  content: "";
  display: block;
  height: 1px;
  background: #353a3c;;
  position: absolute;
  top: 1.5em;
  left: 0;
  right: 0;
  transform: scale(0, 1);
  transition: transform ease-in-out 250ms;
}

nav .nav-logo:hover::before,
nav .nav-link:hover::before {
  transform: scale(1, 1);
}

/*underline for links end*/

nav .nav-logo {
  list-style: none;
  text-decoration: none;
  font-size: 1.4rem;
  font-weight: 500;
  color: none;
  z-index: 11;
  margin-right: 50%;
  font-family: "Inconsolata", monospace;
}

/*nav-links colors */
nav .nav-link {
  font-size: 1rem;
  font-weight: 400;
  color: none;
  letter-spacing: 0.15rem;
  font-family: "Inconsolata", monospace;
}

/* hover nav link */
nav .nav-logo:hover,
.nav-link:hover {
  transition: all 0.3s ease-in-out;
  color: #2d8197;
  animation: underline 1s ease-in-out;
}

/* hover effect ends */
.nav-item,
.nav-item a {
  list-style: none;
  text-decoration: none;

}

ul.nav-menu {
  margin-bottom: 0;


}

.nav-item {
  margin: 0 1.5rem;
}

.hamburger {
  display: none;
  z-index: 110;
  /* margin: 0 1.5rem; */
}

.bar {
  display: block;
  width: 25px;
  height: 3px;
  margin: 5px auto;
  -webkit-transition: all 0.3s ease-in-out;
  transition: all 0.3s ease-in-out;
  background-color: rgb(40, 40, 40);
  z-index: 110;
}

.nav-menu {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.bar:nth-child(1) {
  width: 25px;
}

.bar:nth-child(2) {
  width: 10px;
}

.bar:nth-child(3) {
  width: 7px;
}

/* Media query to show hamburguer */

@media only screen and (max-width: 768px) {
  .nav-menu {
    width: 85%;
    height: 100%;

    position: fixed;
    left: -100%;
    top: 0rem;
    right: 0%;
    flex-direction: column;
    justify-content: center;
    background-color: #005ec7;
    border-radius: 0 0 10px 10px;
    text-align: center;
    transition: 0.3s;
    box-shadow: 0 10px 27px rgba(0, 0, 0, 0.05);
    z-index: 100;
  }

  .nav-link {
    font-size: 3rem;
    font-weight: 500;
    color: rgb(255, 244, 255, 0.8);
    letter-spacing: 0.1rem;
    margin: 5.5rem 0;
  }

  .nav-menu.active {
    left: 0;
  }

  .nav-item {
    align-items: center;
    color: #000000;
    margin: 4.5rem 0;
    display: flex;
  }

  /* nav links in mobile */
  .nav-item a {
    font-size: 1.8rem;
    margin: 2.5rem 0;
    color: rgba(255, 255, 255, 0.8);

  }

  .hamburger {
    display: block;
    cursor: pointer;

  }

  .hamburger.active .bar:nth-child(2) {
    opacity: 0;
    width: 25px;
  }

  .hamburger.active .bar:nth-child(1) {
    transform: translateY(8px) rotate(45deg);
    width: 25px;
  }

  .hamburger.active .bar:nth-child(3) {
    transform: translateY(-8px) rotate(-45deg);
    width: 25px;
  }

  .navbar {
    justify-content: space-between;
  }
}

/* navbar animation */
.nav-active {
  transform: translateX(0%);
}


</style>