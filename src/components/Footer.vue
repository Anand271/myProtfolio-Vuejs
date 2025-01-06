
  <template>
      <!-- Footer -->
      <section id="footer">
    <div class="footer container">
      <div class="brand">
              <h1><span>S</span>antosh<span>A</span>nand</h1>
            </div>
            <h2>Your Complete Web Solution</h2>
            <div class="social-icon">
              <div class="social-item">
                <a href="https://www.linkedin.com/in/santosh-kumar-anand-96b670231/" target="_blank"><img src="https://img.icons8.com/bubbles/100/000000/linkedin.png" /></a>
              </div>
              <div class="social-item">
                <a href="https://github.com/Anand271" target="_blank"><img src="https://img.icons8.com/bubbles/100/000000/github.png" /></a>
              </div>
              
              <div class="social-item">
                <a  href="mailto:anandsa271@gmail.com" target="_blank"><img src="https://img.icons8.com/bubbles/100/000000/gmail.png" /></a>
              </div>
            </div>

            <a href="https://buymeacoffee.com/sanand">
              <img src="../assets/img/bmc_btn.png" alt="" style="height: 60px; width: 100%; object-fit: fill;">
            </a>
      <p>Copyright © {{ currentYear }} Santosh. All rights reserved</p>
    </div>
  </section>
    <!-- End Footer -->
     
  </template>
  
  <script>
  export default {
    data() {
      return {
        currentYear: new Date().getFullYear(), // Gets the current year
      };
    },
  };
  </script>
  
  <style>
  
  </style>