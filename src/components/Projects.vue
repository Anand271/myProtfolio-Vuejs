<template>


<section id="projects">
    <div class="projects container">
      <div class="projects-header">
        <h1 class="section-title">Recent <span>Projects</span></h1>
      </div>
	  <div class="row">
		<div v-for="project in projects" :key="project.id" class="col-12 col-sm-12 col-md-6 col-lg-4 my-3">
			<div class="card" style="border:1px solid crimson; border-radius: 10px; padding: 2px;">
			<img class="card-img-top" :src="project.image" :alt="project.title" style="border-radius: 10px 10px 0 0;">
			<div class="card-body">
				<h2 class="card-title">{{ project.title }}</h2>
				<p class="card-text">{{ project.shortDescription }}</p>
				<!-- <a href="#" class="btn btn-lg text-light" style="background-color: crimson;">See more...</a> -->
			</div>
		</div>
    </div>
  </div>


      <!-- <div class="all-projects">
        <div class="project-item">
          <div class="project-info">
            <h1>Parking System</h1>
            <h2 class="crimson">DpMobile Parking</h2>
            <p>Our parking system revolutionizes parking management in Denmark. With our mobile application, users can easily find nearby parking spaces, park their vehicles, and pay online. Say goodbye to circling the block in search of a spot—our app makes parking hassle-free and convenient.</p>
			<hr>
			<div class="d-flex align-items-center"> 
				<h3 class="mx-3">Links:</h3>
				<a href="https://dpmobileparking.dk/" target="_blank" style="height: 30px; width: 30px;" class="mx-2"><img src="../assets/img/web.png" alt=""></a>
				<a href="https://play.google.com/store/apps/details?id=dk.dpmobileparking&hl=en_IN" target="_blank" style="height: 30px; width: 30px;" class="mx-2"><img src="../assets/img/app-store.png" alt=""></a>
				<a href="https://apps.apple.com/us/app/dp-mobile-parking/id905632836" target="_blank" style="height: 30px; width: 30px;" class="mx-2"><img src="../assets/img/play-store.png" alt=""></a>
			</div>
          </div>
          <div class="project-img">
            <img src="../assets/img/dpparking.jpg" alt="img">
          </div>
        </div>
        <div class="project-item">
          <div class="project-info">
            <h1>Project 2</h1>
            <h2 class="crimson">Dating app</h2>
            <p>Its dating app, where connections blossom! Whether you're looking for love or companionship, our platform lets you register and find like-minded individuals based on your interests. Swipe, like, and chat with potential matches, and stay updated with their online status. Find your perfect match with ease and embark on a journey to meaningful relationships!</p>
          </div>
          <div class="project-img">
            <img src="https://d540vms5r2s2d.cloudfront.net/mad/uploads/mad_blog_602a2ab3469971613376179.png" alt="img">
          </div>
        </div>
        <div class="project-item">
          <div class="project-info">
            <h1>Project 3</h1>
            <h2 class="crimson">Mr Management</h2>
            <p>Our outdoor employee management system streamlines task allocation and tracking. Employees can input their tasks for the upcoming days, while managers can efficiently assign tasks, set targets, and monitor progress in real-time. With dynamic updates, the system ensures seamless coordination and optimal productivity for every project.</p>
          </div>
          <div class="project-img">
            <img src="https://www.pockethrms.com/wp-content/uploads/2022/01/Happy-Workforce.jpg" alt="img">
          </div>
        </div>
        <div class="project-item">
          <div class="project-info">
            <h1>Project 4</h1>
            <h2 class="crimson">Document Management</h2>
            <p>Our document management system offers a comprehensive solution for companies seeking efficient document processing. Documents can progress through various stages, with approvals required from different roles within the organization. The system facilitates document initiation, assignment to employees, and other essential functionalities, ensuring smooth workflow and compliance with organizational procedures.</p>
          </div>
          <div class="project-img">
            <img src="https://static.helpjuice.com/helpjuice_production/uploads/upload/image/4752/direct/1591662767267-Document%20Management%20Software.png" alt="img">
          </div>
        </div>
      </div> -->
    </div>
  </section>

  <!-- End Projects Section -->
    <SingleProject v-if="showModal"/>
</template>

<script>
import SingleProject from '@/components/SingleProject.vue'

export default {
   data(){
    return{
      showModal: false,
	  projects: [],
    }
   },
   mounted() {
    this.loadProjects();
  },
    methods:{
      openProject(){
        this.showModal = true
        console.log(this.showModal)
      },
	  async loadProjects() {
      try {
        const response = await fetch('/data/projects.json');
        if (!response.ok) throw new Error('Failed to load projects');
        this.projects = await response.json();
      } catch (error) {
        console.error(error);
      }
    },
    },
    components:{
      SingleProject
    }
}
</script>

<style>

@import url("https://fonts.googleapis.com/css2?family=Baloo+2&display=swap");


/* This pen */
 /* body {
	 font-family: "Baloo 2", cursive;
	 font-size: 16px;
	 color: #fff;
	 text-rendering: optimizeLegibility;
	 font-weight: initial;
}
 .dark {
	 background: #110f16;
}
 .light {
	 background: #f3f5f7;
}
 a, a:hover {
	 text-decoration: none;
	 transition: color 0.3s ease-in-out;
}
 #pageHeaderTitle {
	 margin: 2rem 0;
	 text-transform: uppercase;
	 text-align: center;
	 font-size: 2.5rem;
}



 .postcard {
	 flex-wrap: wrap;
	 display: flex;
	 box-shadow: 0 4px 21px -12px rgba(0, 0, 0, 0.66);
	 border-radius: 10px;
	 margin: 0 0 2rem 0;
	 overflow: hidden;
	 position: relative;
	 color: #fff;
}
 .postcard.dark {
	 background-color: #18151f;
}
 .postcard.light {
	 background-color: #e1e5ea;
}
 .postcard .t-dark {
	 color: #18151f;
}
 .postcard a {
	 color: inherit;
}
 .postcard h1, .postcard .h1 {
	 margin-bottom: 0.5rem;
	 font-weight: 500;
	 line-height: 1.2;
}
 .postcard .small {
	 font-size: 80%;
}
 .postcard .postcard__title {
	 font-size: 1.75rem;
}
 .postcard .postcard__img {
	 max-height: 180px;
	 width: 100%;
	 object-fit: cover;
	 position: relative;
}
 .postcard .postcard__img_link {
	 display: contents;
}
 .postcard .postcard__bar {
	 width: 50px;
	 height: 10px;
	 margin: 10px 0;
	 border-radius: 5px;
	 background-color: #424242;
	 transition: width 0.2s ease;
}
 .postcard .postcard__text {
	 padding: 1.5rem;
	 position: relative;
	 display: flex;
	 flex-direction: column;
}
 .postcard .postcard__preview-txt {
	 overflow: hidden;
	 text-overflow: ellipsis;
	 text-align: justify;
	 height: 100%;
}
 .postcard .postcard__tagbox {
	 display: flex;
	 flex-flow: row wrap;
	 font-size: 14px;
	 margin: 20px 0 0 0;
	 padding: 0;
	 justify-content: center;
}
 .postcard .postcard__tagbox .tag__item {
	 display: inline-block;
	 background: rgba(83, 83, 83, 0.4);
	 border-radius: 3px;
	 padding: 2.5px 10px;
	 margin: 0 5px 5px 0;
	 cursor: default;
	 user-select: none;
	 transition: background-color 0.3s;
}
 .postcard .postcard__tagbox .tag__item:hover {
	 background: rgba(83, 83, 83, 0.8);
}
 .postcard:before {
	 content: "";
	 position: absolute;
	 top: 0;
	 right: 0;
	 bottom: 0;
	 left: 0;
	 background-image: linear-gradient(-70deg, #424242, transparent 50%);
	 opacity: 1;
	 border-radius: 10px;
}
 .postcard:hover .postcard__bar {
	 width: 100px;
}
 @media screen and (min-width: 769px) {
	 .postcard {
		 flex-wrap: inherit;
	}
	 .postcard .postcard__title {
		 font-size: 2rem;
	}
	 .postcard .postcard__tagbox {
		 justify-content: start;
	}
	 .postcard .postcard__img {
		 max-width: 300px;
		 max-height: 100%;
		 transition: transform 0.3s ease;
	}
	 .postcard .postcard__text {
		 padding: 3rem;
		 width: 100%;
	}
	 .postcard .media.postcard__text:before {
		 content: "";
		 position: absolute;
		 display: block;
		 background: #18151f;
		 top: -20%;
		 height: 130%;
		 width: 55px;
	}
	 .postcard:hover .postcard__img {
		 transform: scale(1.1);
	}
	 .postcard:nth-child(2n+1) {
		 flex-direction: row;
	}
	 .postcard:nth-child(2n+0) {
		 flex-direction: row-reverse;
	}
	 .postcard:nth-child(2n+1) .postcard__text::before {
		 left: -12px !important;
		 transform: rotate(4deg);
	}
	 .postcard:nth-child(2n+0) .postcard__text::before {
		 right: -12px !important;
		 transform: rotate(-4deg);
	}
}
 @media screen and (min-width: 1024px) {
	 .postcard__text {
		 padding: 2rem 3.5rem;
	}
	 .postcard__text:before {
		 content: "";
		 position: absolute;
		 display: block;
		 top: -20%;
		 height: 130%;
		 width: 55px;
	}
	 .postcard.dark .postcard__text:before {
		 background: #18151f;
	}
	 .postcard.light .postcard__text:before {
		 background: #e1e5ea;
	}
}



 .postcard .postcard__tagbox .green.play:hover {
	 background: #79dd09;
	 color: black;
}
 .green .postcard__title:hover {
	 color: #79dd09;
}
 .green .postcard__bar {
	 background-color: #79dd09;
}
 .green::before {
	 background-image: linear-gradient(-30deg, rgba(121, 221, 9, 0.1), transparent 50%);
}
 .green:nth-child(2n)::before {
	 background-image: linear-gradient(30deg, rgba(121, 221, 9, 0.1), transparent 50%);
}
 .postcard .postcard__tagbox .blue.play:hover {
	 background: #0076bd;
}
 .blue .postcard__title:hover {
	 color: #0076bd;
}
 .blue .postcard__bar {
	 background-color: #0076bd;
}
 .blue::before {
	 background-image: linear-gradient(-30deg, rgba(0, 118, 189, 0.1), transparent 50%);
}
 .blue:nth-child(2n)::before {
	 background-image: linear-gradient(30deg, rgba(0, 118, 189, 0.1), transparent 50%);
}
 .postcard .postcard__tagbox .red.play:hover {
	 background: #bd150b;
}
 .red .postcard__title:hover {
	 color: #bd150b;
}
 .red .postcard__bar {
	 background-color: #bd150b;
}
 .red::before {
	 background-image: linear-gradient(-30deg, rgba(189, 21, 11, 0.1), transparent 50%);
}
 .red:nth-child(2n)::before {
	 background-image: linear-gradient(30deg, rgba(189, 21, 11, 0.1), transparent 50%);
}
 .postcard .postcard__tagbox .yellow.play:hover {
	 background: #bdbb49;
	 color: black;
}
 .yellow .postcard__title:hover {
	 color: #bdbb49;
}
 .yellow .postcard__bar {
	 background-color: #bdbb49;
}
 .yellow::before {
	 background-image: linear-gradient(-30deg, rgba(189, 187, 73, 0.1), transparent 50%);
}
 .yellow:nth-child(2n)::before {
	 background-image: linear-gradient(30deg, rgba(189, 187, 73, 0.1), transparent 50%);
}
 @media screen and (min-width: 769px) {
	 .green::before {
		 background-image: linear-gradient(-80deg, rgba(121, 221, 9, 0.1), transparent 50%);
	}
	 .green:nth-child(2n)::before {
		 background-image: linear-gradient(80deg, rgba(121, 221, 9, 0.1), transparent 50%);
	}
	 .blue::before {
		 background-image: linear-gradient(-80deg, rgba(0, 118, 189, 0.1), transparent 50%);
	}
	 .blue:nth-child(2n)::before {
		 background-image: linear-gradient(80deg, rgba(0, 118, 189, 0.1), transparent 50%);
	}
	 .red::before {
		 background-image: linear-gradient(-80deg, rgba(189, 21, 11, 0.1), transparent 50%);
	}
	 .red:nth-child(2n)::before {
		 background-image: linear-gradient(80deg, rgba(189, 21, 11, 0.1), transparent 50%);
	}
	 .yellow::before {
		 background-image: linear-gradient(-80deg, rgba(189, 187, 73, 0.1), transparent 50%);
	}
	 .yellow:nth-child(2n)::before {
		 background-image: linear-gradient(80deg, rgba(189, 187, 73, 0.1), transparent 50%);
	}
}
  */

</style>