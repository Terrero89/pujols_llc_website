<script setup lang="ts">
import {onMounted,onBeforeUnmount, ref} from "vue"
const isScrolled = ref(false);

const menuIsVisible = ref(false);
const updateScroll = () => {
  if (document.body.scrollTop > 50 || document.documentElement.scrollTop > 50) {
    isScrolled.value = true;
  } else {
    isScrolled.value = false;
  }
};

const toggleOn = () => {
  menuIsVisible.value = !menuIsVisible.value;
};

onMounted(() => {
  window.addEventListener("scroll", updateScroll);
  updateScroll(); // Call initially to set state
});

onBeforeUnmount(() => {
  window.removeEventListener("scroll", updateScroll);
});
</script>

<template>
  <div>
    <nav
      class="navbar"
      :class="{ navbarOn: isScrolled, navbarOff: !isScrolled }"
    >
      <a href="#" :class="[{ font: isScrolled }]" class="nav-logo"
        >Pujols Roofing LLC</a
      >
      <ul class="nav-menu" :class="[{ active: menuIsVisible }]">
        <li class="nav-item">
          <a :class="{ font: isScrolled }" href="#about-section">About Us</a>
        </li>
        <li class="nav-item">
          <a :class="{ font: isScrolled }" href="#services-section">Services</a>
        </li>
        <li class="nav-item">
          <a :class="{ font: isScrolled }" href="#gallery-section">Gallery</a>
        </li>
        <li class="nav-item">
          <a :class="{ font: isScrolled }" href="#contact-section">Contact</a>
        </li>
      </ul>
      <div
        class="hamburger"
        @click="toggleOn"
        :class="[{ active: menuIsVisible }]"
      >
        <span class="bar"></span>
        <span class="bar"></span>
        <span class="bar"></span>
      </div>
    </nav>
  </div>
</template>

<style scoped>
.nav-item .font {
  color: white;
  transition: all 0.3s ease-out;
}

.nav-logo {
  font-size: 1.2rem;
  font-weight: bold;
  color: #2c2c2c;
  list-style: none;
  text-decoration: none;
}
.nav-logo.font {
  color: white;
  transition: all 0.3s ease-out;
}

.navbar {
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  padding: 1rem 2rem;
  background-color: #fff;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1); /* Optional subtle shadow */
  position: fixed; /* Stack on top */
  top: 0;
  left: 0;
  width: 100%;
  z-index: 10; /* Ensure navbar stays on top */
  transition: background 600ms ease-out; /* Animation for scroll effect */
}

.nav-menu {
  display: flex;
  list-style: none;
  margin: 0;
  padding: 0;
}

.nav-item {
  margin-right: 1.5rem;
}

.nav-item a {
  text-decoration: none;
  color: #333;
}

.nav-item a:hover {
  color: #007bff; /* Optional hover color */
}

/* Style for navbar background color change on scroll */
.navbarOn {
  background-color: #8b8b8b;
  /* backdrop-filter: blur(10px); */
  transition: background 600ms ease-out;
}

/* Hamburger menu styles */
.hamburger {
  display: none;
  z-index: 110;
  cursor: pointer;
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
  justify-content: space-between;
  align-items: center;
}

.bar:nth-child(1) {
  width: 25px;
}

.bar:nth-child(2) {
  width: 25px;
}

.bar:nth-child(3) {
  width: 25px;
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
    background-color: #f3f3f3;
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
    font-size: 3rem;

    align-items: center;
    color: #000000;
    margin: 4.5rem 0;
    display: flex;
  }

  /* nav links in mobile */
  .nav-item a {
    font-size: 1.1rem;
    margin: 2.5rem 0;
    color: rgba(39, 39, 39, 0.8);
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
