<template>
<section id="projects">
    <div class="projects container">
      <div class="projects-header">
        <h1 class="section-title">Recent <span>Projects</span></h1>
      </div>
	  <div class="row">
		<div v-for="project in projects" :key="project.id" class="col-12 col-sm-12 col-md-6 col-lg-4 my-3 open-modal-trigger" @click="openProject(project.id)">
			<div class="card">
			<img class="card-img-top" :src="project.image" :alt="project.title" style="border-radius: 10px 10px 0 0;">
			<div class="card-body">
				<h2 class="card-title">{{ project.title }}</h2>
			</div>
		</div>
    </div>
  </div>
    </div>
  </section>

  <!-- End Projects Section -->


  <!-- Modal structure -->
  <div
      class="modal fade bd-example-modal-xl"
      id="exampleModal"
      tabindex="-1"
      aria-labelledby="exampleModalLabel"
      aria-hidden="true"
    >
      <div class="modal-dialog modal-xl">
        <div class="modal-content">
          <div class="modal-header">
            <h1 class="modal-title" id="exampleModalLabel">{{project.title}}</h1>
            <button
              type="button"
              class="btn-close"
              data-bs-dismiss="modal"
              aria-label="Close"
            ></button>
          </div>
          <div class="modal-body">
            <div v-if="showLoader" id="loading-test-1" class="loading-main-div w-100"> 
              <div class="loading-mdb">
                <div class="spinner-border loading-icon" style="width: 3rem; height: 3rem;" role="status" ></div>
                <!-- <span class="loading-text">Loading...</span> -->
              </div>
            </div>
            <div v-if="!showLoader" class="row">
              <div class="col-12 col-md-4 col-sm-12 col-xl-4 left-column custom-scroller">
                <div class="content" ref="leftColumn">
                  <!-- Description Area -->
                  <div class="left-heading-div">
                    <h2>Description</h2>
                    <p>{{project.description}}</p>
                  </div>

                  <!-- Technologies area -->
                  <div class="left-heading-div">
                    <h2 class="my-2">Technologies</h2>
                    <div>
                      <div class="mx-2 category-skills">
                        <span class="skill-tag" v-for="(tech, index) in project.tech" :key="index">{{tech}}</span>
                      </div>
                    </div>
                  </div>

                  <!-- Client Goal Area -->
                  <div class="left-heading-div">
                    <h2>Client Goals</h2>
                    <p>{{project.clientGoals}}</p>
                  </div>

                  <!-- My Contribution Area -->
                   <div class="left-heading-div">
                    <h2>My Contribution</h2>
                    <ul>
                      <li v-for="(point, index) in project.myContributionPoints" :key="index">{{point}}</li>
                    </ul>
                   </div>
                </div>
              </div>
              <div class="col-12 col-md-8 col-sm-12 col-xl-8 right-column custom-scroller" ref="rightColumn">
                <h2 class="text-center">Gallery</h2>
                <div class="content" >
                  <div>
                    <img :src="project.image" :alt="project.title">
                  </div>
                  <div class="my-2" v-for="(img, index) in project.images" :key="index">
                    <img :src="img" alt="">
                  </div>

                  <br>
                  <hr>
                  <br>
                  <!-- more project area -->
                  <div>
                    <h2 class="underline">More Projects</h2>
                    <div class="row">
                      <div v-for="project in projectElseOpened" :key="project.id" class="col-12 col-sm-12 col-md-6 col-lg-4 my-3 open-modal-trigger" @click="changeProject(project.id)">
                        <div class="card">
                        <img class="card-img-top" :src="project.image" :alt="project.title" style="border-radius: 10px 10px 0 0;">
                        <div class="card-body">
                          <h4 class="card-title">{{ project.title }}</h4>
                        </div>
                      </div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="modal-footer">
            <button
              type="button"
              class="btn btn-secondary"
              data-bs-dismiss="modal"
            >
              Close
            </button>
          </div>
        </div>
      </div>
    </div>
</template>

<script>
import { Modal } from 'bootstrap';

export default {
  data() {
    return {
      showModal: false,
      projects: [],
      projectElseOpened: [],
      project:{},
      showLoader: false,
    };
  },
  mounted() {
    this.loadProjects();
  },
  methods: {
    openProject(id) {
     const modal = new Modal(document.getElementById("exampleModal"));
     this.project = this.projects.find(x=>x.id === id);

     this.projectElseOpened = this.projects.filter(x=>x.id != id);
     modal.show();
    },
    changeProject(id){

      //showing empty screen for 700ms
      this.showLoader = true;
      setTimeout(() => {
        this.showLoader = false;
      }, 700);

      this.scrollToTop();

      this.projectElseOpened = this.projects.filter(x=>x.id != id);
      this.project = this.projects.find(x=>x.id === id);
    },
    scrollToTop() {
      // Scroll the left column to the top
      this.$refs.leftColumn.scrollTop = 0;
      console.log('left div', this.$refs.leftColumn.scrollTop);
      // Scroll the right column to the top
      this.$refs.rightColumn.scrollTop = 0;
      console.log('right div', this.$refs.rightColumn.scrollTop);
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
  }
};
</script>

<style scoped>

/* custom scroller */

.custom-scroller::-webkit-scrollbar-track
{
	-webkit-box-shadow: inset 0 0 6px rgba(0,0,0,0.3);
	border-radius: 10px;
	background-color: #F5F5F5;
}

.custom-scroller::-webkit-scrollbar
{
	width: 12px;
	background-color: #F5F5F5;
}

.custom-scroller::-webkit-scrollbar-thumb
{
	border-radius: 10px;
	-webkit-box-shadow: inset 0 0 6px rgba(0,0,0,.3);
	background-color: #555;
}

.loading-main-div{
  display: flex;
  background-color: rgb(227, 227, 227);
  border-radius: 10px;
  justify-content: center;
  align-items: center;
  height: 80vh;
}

.left-heading-div{
  margin: 1.5rem 0 0 0;
}

.left-heading-div h2, .underline{
  display: inline-block;
  border-bottom: 1.5px solid crimson;
}

.left-heading-div ul li, .left-heading-div p {
  font-size: 1.5em;
  font-weight: 400;
}


.card{
    box-shadow: 0px 0px 18px 0 #0000002c;
	border-radius: 10px;
	cursor: pointer; 
}

.card:hover{
    box-shadow: 0px 0px 5px 0 #0000002c;
}

.modal-body {
  display: flex;
}

.left-column,
.right-column {
  max-height: 80vh; /* Set this to the desired height */
  overflow-y: auto; /* Enable scrolling */
}

.content {
  padding: 10px; /* Optional padding for inner content */
}

.tech{
  padding: 5px 10px;
  border-radius: 7px;
  background-color: rgb(174, 174, 174);
}

.category-skills{
    display: flex;
    flex-wrap: wrap; /* Allows items to wrap to the next line */
    gap: 10px; /* Optional: Adds space between skill tags */
    align-items: center;
    justify-content: center;
}

.skill-tag {
    display: inline-block;
    align-items: center;
    flex: 1 1 auto; 
    max-width: fit-content; /* Keeps tags from growing too wide */
    background-color: blank;
    border: 1px solid crimson;
    cursor: context-menu;
    padding: 5px 10px;
    border-radius: 12px;
    margin: 5px 0 0 0;
    font-size: 1.5em;
    font-weight: 600;
}

</style>