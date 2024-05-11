<template>
 <Nav />
 <Hero />
 <Services />
 <Projecs />
 <About />
 <Contact />
 <Footer />
</template>

<script>
// @ is an alias to /src
import Nav from '@/components/Nav.vue'
import Hero from '@/components/Hero.vue'
import Services from '@/components/Services.vue'
import Projecs from '@/components/Projects.vue'
import About from '@/components/About.vue'
import Contact from '@/components/Contact.vue'
import Footer from '@/components/Footer.vue'

export default {
  name: 'HomeView',
  components: {
    Nav, Hero, Services, Projecs, About, Contact, Footer
  }
}
</script>
