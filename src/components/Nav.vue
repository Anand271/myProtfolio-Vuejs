<template>
  <!-- Header -->
  <section id="header">
    <div class="header container" :style="{ backgroundColor: headerBgColor }">
      <div class="nav-bar">
        <div class="brand">
          <a href="#hero">
            <h1><span>S</span>antosh <span>A</span>nand</h1>
          </a>
        </div>
        <div class="nav-list">
          <div class="hamburger" :class="{ active: isHamburgerActive }" @click="toggleMenu">
            <div class="bar"></div>
          </div>
          <ul :class="{ active: isMenuActive }">
            <li><a href="#about" @click="closeMenu">About</a></li>
            <li><a href="#skills" @click="closeMenu">Skill</a></li>
            <li><a href="#projects" @click="closeMenu">Projects</a></li>
            <li><a href="#contact" @click="closeMenu">Contact</a></li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { ref, onMounted, onUnmounted } from 'vue';

export default {
  setup() {
    const isHamburgerActive = ref(false);
    const isMenuActive = ref(false);
    const headerBgColor = ref('transparent');

    const toggleMenu = () => {
      isHamburgerActive.value = !isHamburgerActive.value;
      isMenuActive.value = !isMenuActive.value;
    };

    const closeMenu = () => {
      isHamburgerActive.value = false;
      isMenuActive.value = false;
    };

    const handleScroll = () => {
      headerBgColor.value = window.scrollY > 250 ? '#29323c' : 'transparent';
    };

    onMounted(() => {
      window.addEventListener('scroll', handleScroll);
    });

    onUnmounted(() => {
      window.removeEventListener('scroll', handleScroll);
    });

    return {
      isHamburgerActive,
      isMenuActive,
      headerBgColor,
      toggleMenu,
      closeMenu
    };
  }
};
</script>

<style scoped>
.header {
  transition: background-color 0.3s ease;
}

</style>