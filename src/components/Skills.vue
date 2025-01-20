<template>
    <section id="skills">
        <div class="skills-section row align-items-center justify-content-center">
            <h1 class="section-title">M<span>y</span> Sk<span>i</span>lls</h1>
    <div class="category m-3 col-12 col-lg-4 col-md-6 col-sm-12">
        <h2 class="category-header">Frameworks</h2>
        <div class="category-skills">
            <span class="skill-tag">Angular <i class="fa-brands fa-angular"></i></span>
            <span class="skill-tag">.Net core </span>
        </div>
    </div>
    <div class="category m-3 col-12 col-lg-4 col-md-6 col-sm-12">
        <h2 class="category-header">Databases</h2>
        <div class="category-skills">
            <span class="skill-tag">MS SQL <i class="fa-solid fa-database"></i></span>
            <span class="skill-tag">MySQL </span>
            <span class="skill-tag">Postgres Sql</span>
        </div>
    </div>
    <div class="category m-3 col-12 col-lg-4 col-md-6 col-sm-12">
        <h2 class="category-header">Identity</h2>
        <div class="category-skills">
            <span class="skill-tag">Keycloak <i class="fa-solid fa-key"></i></span>
            <span class="skill-tag">IdentityServer4</span>
            <span class="skill-tag">ASP.NET Core Identity</span>
        </div>
    </div>
    <div class="category m-3 col-12 col-lg-4 col-md-6 col-sm-12">
        <h2 class="category-header">Tools</h2>
        <div class="category-skills">
            <span class="skill-tag"><i class="fa-brands fa-git"></i> <i class="fa-solid fa-code-branch"></i></span>
            <span class="skill-tag">Docker <i class="fa-brands fa-docker"></i></span>
            <span class="skill-tag">Jira <i class="fa-brands fa-jira"></i></span>
            
        </div>
    </div>
    <div class="category m-3 col-12 col-lg-4 col-md-6 col-sm-12">
        <h2 class="category-header">libraries</h2>
        <div class="category-skills">
            <span class="skill-tag">Syncfusion</span>
            <span class="skill-tag">Bootstrap <i class="fa-brands fa-bootstrap"></i></span>
            <span class="skill-tag">J Query </span>
        </div>
    </div>
    <div class="category m-3 col-12 col-lg-4 col-md-6 col-sm-12">
        <h2 class="category-header">IDEs</h2>
        <div class="category-skills">
            <span class="skill-tag">Visual Studio <i class="fa-solid fa-code"></i></span>
            <span class="skill-tag">VS Code</span>
        </div>
    </div>
    <div class="category m-3 col-12 col-lg-4 col-md-6 col-sm-12">
        <h2 class="category-header">Pattern</h2>
        <div class="category-skills">
            <span class="skill-tag">Microservices</span>
            <span class="skill-tag">Repository</span>
        </div>
    </div>
</div>



</section>
<!-- <iframe src="https://cdn.botpress.cloud/webchat/v2.2/shareable.html?configUrl=https://files.bpcontent.cloud/2024/12/17/12/20241217125253-GAMG1LD1.json" 
frameborder="0" style="width:auto; height: 80vh;"></iframe> -->
</template>

<script>
export default {

}
</script>

<style scoped>

#skills{
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
}

.skills-section {
    padding: 20px;
    color: blank;
}

.category {
    padding: 15px;
    border-radius: 8px;
    border-radius: 10px;
    box-shadow: 0px 0px 18px 0 #0000002c;
}

.category:hover{
    box-shadow: 0px 0px 5px 0 #0000002c;
}

.category-header {
    font-weight: bold;
    font-size: 1..8em;
    margin-bottom: 10px;
    text-align: center;
    /* border-bottom: 1.5px solid crimson; */
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
    margin: 5px 0;
    font-size: 1.5em;
    font-weight: 600;
    transition: all 0.3s ease; /* Smooth transition effect */
}

.skill-tag i {
    margin-left: 5px; /* Adds space between text and icon */
}

.skill-tag:hover{
    background-color: crimson;
    color: #fff;
    transform: scale(1.15);
}

</style>