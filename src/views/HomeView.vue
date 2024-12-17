<template>
 <Nav />
 <Hero />
 <About />
 <VideoIntro/>
 <Skills />
 <Projecs />
 <Contact />
 <Footer />

  <!-- Chat iframe -->
  <div v-if="showChat" class="chat-container">
    <iframe 
      src="https://cdn.botpress.cloud/webchat/v2.2/shareable.html?configUrl=https://files.bpcontent.cloud/2024/12/17/13/20241217134012-AWSGHJSE.json" 
      class="chat-iframe" 
      frameborder="0">
    </iframe>
  </div>

 <!-- Scroll-to-Top Button -->
 <button class="scroll-to-top" @click="toggleChat">
  <i :class="chatBtnCls"></i>
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
import VideoIntro from '@/components/VideoIntro.vue'

export default {
  name: 'HomeView',
  data() {
    return {
      showScrollButton: false, // Controls the visibility of the button
      showChat: false,
      chatBtnCls: 'fa-solid fa-comments',
    };
  },
  components: {
    Nav, Hero, Projecs, About, Contact, Footer, Skills, VideoIntro
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
    toggleChat() {
      this.showChat = !this.showChat; // Toggle the chat iframe visibility
      if(this.showChat){
        this.chatBtnCls = 'fa-solid fa-xmark';
      }else{
        this.chatBtnCls = 'fa-solid fa-comments';
      }
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
    padding: 10px;
    color: #fff;
    border: none;
    border-radius: 50%;
    width: 40px;
    height: 40px;
    font-size: 1.5rem;
    cursor: pointer;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
    transition: opacity 0.3s ease, transform 0.3s ease;
    z-index: 1001;
}

.chat-container {
  position: fixed;
  bottom: 80px; /* Adjust the position above the button */
  right: 20px;
  width: 350px; /* Chat window width */
  height: 500px; /* Chat window height */
  z-index: 1000; /* Ensures the chat is above the UI */
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.2);
}

.chat-iframe {
  width: 100%;
  height: 100%;
  border-radius: 10px; /* Rounded corners */
  border: 1px solid #fff;
}

.scroll-to-top:hover {
    opacity: 0.8;
    transform: scale(1.1); 
}

</style>
