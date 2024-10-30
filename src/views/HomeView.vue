<template>
 <Nav />
 <Hero />
 <About />
 <Skills />
 <Projecs />
 <Contact />
 <Footer />

 <!-- Scroll-to-Top Button -->
 <button v-if="showScrollButton" class="scroll-to-top" @click="scrollToTop">
  <i class="fa-solid fa-arrow-up"></i>
    </button>
</template>

<script>
// @ is an alias to /src
import Nav from '@/components/Nav.vue'
import Hero from '@/components/Hero.vue'
import Skills from '@/components/Skills.vue'
import Projecs from '@/components/Projects.vue'
import About from '@/components/About.vue'
import Contact from '@/components/Contact.vue'
import Footer from '@/components/Footer.vue'

export default {
  name: 'HomeView',
  data() {
    return {
      showScrollButton: false, // Controls the visibility of the button
    };
  },
  components: {
    Nav, Hero, Projecs, About, Contact, Footer, Skills
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll); // Add scroll event listener on mount
  },
  beforeDestroy() {
    window.removeEventListener("scroll", this.handleScroll); // Clean up listener on destroy
  },
  methods: {
    handleScroll() {
      this.showScrollButton = window.scrollY > window.innerHeight; // Show button if scrolled more than 100vh
    },
    scrollToTop() {
      window.scrollTo({
        top: 0,
        behavior: "smooth", // Smooth scrolling
      });
    },
  },
}
</script>

<style>
.scroll-to-top {
    position: fixed;
    bottom: 20px;
    right: 20px;
    background-color: crimson;
    color: #fff;
    border: none;
    border-radius: 50%;
    width: 40px;
    height: 40px;
    font-size: 1.5rem;
    cursor: pointer;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
    transition: opacity 0.3s ease, transform 0.3s ease;
}

.scroll-to-top:hover {
    opacity: 0.8;
    transform: scale(1.1); /* Slight enlargement on hover */
}

</style>
