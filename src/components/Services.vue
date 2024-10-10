<template>
   <!-- Service Section -->
   <section id="services">
    <div class="services container">
      <div class="service-top">
        <h1 class="section-title">Serv<span>i</span>ces</h1>
        <p>"I'm a freelance web developer offering a range of services including web development, landing pages, mobile apps, full-stack development, and chatbots. With expertise in Angular and .NET Core, I can help bring your ideas to life with efficient and high-quality solutions."</p>
      </div>
      <div class="service-bottom">
        <div class="service-item service-item-1" :style="{ backgroundImage: 'url(' + require('@/assets/img/custom-website.png') + ')' }">
          <div class="icon"><img src="../assets/img/landing-page.png"  style="height: 60px; width: 60px;"  /></div>
          <h2>Custom Websites </h2>
          <p>We offer custom website development, creating user-friendly, responsive websites to meet your business needs and enhance your online presence effectively.</p>
        </div>
        <div class="service-item service-item-2" :style="{ backgroundImage: 'url(' + require('@/assets/img/mobile-app.jpg') + ')' }">
          <div class="icon"><img src="../assets/img/booking.png" style="height: 60px; width: 60px;" /></div>
          <h2>Mobile apps</h2>
          <p>We create custom mobile apps, offering personalized, high-performance solutions designed to meet your business needs for both Android and iOS platforms.</p>
        </div>
        <div class="service-item service-item-3" :style="{ backgroundImage: 'url(' + require('@/assets/img/backend-developemnt.jpg') + ')' }">
          <div class="icon"><img src="../assets/img/backend.png"  style="height: 60px; width: 60px;"/></div>
          <h2>Backend Development</h2>
          <p>We provide backend development services, building secure and efficient systems to ensure smooth functionality and seamless performance for your applications.</p>
        </div>
        <div class="service-item service-item-4" :style="{ backgroundImage: 'url(' + require('@/assets/img/full_stack_development.jpg') + ')' }">
          <div class="icon"><img src="../assets/img/coding.png" style="height: 70px; width: 70px;" /></div>
          <h2>Full Stack Web</h2>
          <p>We provide full stack development services, building complete, scalable web solutions that cover both frontend and backend to meet your business needs efficiently.</p>
        </div>
      </div>
    </div>
  </section>
  <!-- End Service Section -->
</template>

<script>
export default {

}
</script>

<style>

</style>