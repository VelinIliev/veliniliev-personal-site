<template>
	<div class="wrapper">
		<div class="line"></div>
		<div class="skill">Work</div>
		<h2>My Portfolio</h2>
		<div class="project-wrapper">
			<div class="image" v-for="item in projects" :key="item.id" @click="openModal(item.id)">
				<img :src="item.image">
			</div>
		</div>
	</div>
	<div id="myModal" :class="['modal', modalActive ? 'active' : '']">
		<div class="modal-content">
			<div class="top-row">
				<div class="project-name"> {{ activElement.name }}</div>
				<div class="close" @click="closeModal()">&times;</div>
			</div>
			<div class="project-image">
				<img :src="activElement.image">
			</div>
			<div class="description">{{activElement.description}}</div>
			<div class="project-links">
				<div v-if="activElement.liveLink" class="link">
					<a :href="activElement.liveLink" target="_blank">Live</a>
				</div>
				<div v-if="activElement.codeLink" class="link">
					<a :href="activElement.codeLink" target="_blank">Code</a>
				</div>
				<div v-if="activElement.frontEndLink" class="link">
					<a :href="activElement.frontEndLink" target="_blank">Front End</a>
				</div>
				<div v-if="activElement.backEndLink" class="link">
					<a :href="activElement.backEndLink" target="_blank">Back End</a>
				</div>
			</div>
			<div class="btnHolder">
				<button class="btn" @click="closeModal()">Close</button>
			</div>
		</div>
	</div>
</template>

<script setup>
import {ref} from "vue";

let modalActive = ref(false);
let activElement = ref("")

function openModal(value) {
	modalActive.value = true
	activElement = projects[value]

}
function closeModal() {
	modalActive.value = false;
	activElement = ""
}
let projects = [
	{
		id: 0,
		image: "images/personal-site.png",
		name: "Personal site",
		description: "My personal page, build with VueJs and deployed to github pages.",
		liveLink: "https://veliniliev.github.io/veliniliev-personal-site/",
		codeLink: "https://github.com/VelinIliev/veliniliev-personal-site",
		frontEndLink: "",
		backEndLink: ""
	},
	{
		id: 1,
		image: "images/kitchen-helper.png",
		name: "Kitchen Helper",
		description: "Kitchen Helper is an innovative project developed for SoftUni Intern and Team Lead Academy, " +
				"designed to revolutionize the culinary experience. This cutting-edge application is a recipe hub " +
				"powered by an advanced AI generator, offering users a seamless and enhanced search functionality based on " +
				"ingredients. The robust back-end of Kitchen Helper is built on a foundation of powerful technologies, " +
				"including FastAPI, Nginx, Uvicorn, Celery, PostgreSQL and gRPC. These components work together seamlessly " +
				"to ensure efficient data processing, storage, and retrieval. On the front-end, we've leveraged the " +
				"capabilities of Vue.js, Axios, Pinia, and Bootstrap to create a user-friendly interface that enhances " +
				"the overall experience. Kitchen Helper is not just a recipe app; it's a testament to the fusion of " +
				"technology and culinary arts, providing users with a sophisticated platform to explore, discover, " +
				"and create delightful dishes with ease.",
		liveLink: "https://kitchenhelper.eognyanov.com/",
		codeLink: "",
		frontEndLink: "https://github.com/eognianov/kitchen-helper-frontend",
		backEndLink: "https://github.com/eognianov/kitchen-helper-backend"
	},
	{
		id: 2,
		image: "images/ctrs.png",
		name: "CTRS project",
		description: "Developed a Server Side Rendering project aimed at facilitating cinema ticket reservations. " +
				"This dynamic web application was crafted using a robust tech stack, including Django for the backend, " +
				"Django REST framework for API development, Django Template Language for efficient template rendering, " +
				"and a seamless integration of HTML, CSS, and JavaScript for a responsive and engaging user interface. " +
				"The utilization of these technologies ensures a high-performance and user-friendly experience for " +
				"individuals navigating the cinema ticket reservation process.",
		liveLink: "",
		codeLink: "https://github.com/VelinIliev/CTRS-project",
		frontEndLink: "",
		backEndLink: ""
	},
]
</script>

<style scoped>
.wrapper {
	flex-direction: column;
	text-align: left;
}
.project-wrapper {
	width: 100%;
	display: flex;
	gap: 1rem;
	flex-wrap: wrap;
	justify-content: space-between;
	margin-top: 2rem;
	background-color: var(--vi-light-dark);
	padding: 1rem;
}
.image {
	cursor: pointer;
	width: 49%;
	height: 24rem;
	border-radius: 1rem;
	overflow: hidden;
	transition: all .3s;
}
.image:hover {
	transform: scale(1.05);
	transition: all .3s;
}
.image img {
	object-fit: cover;
	width: 100%;
	height: 100%;
}
.skill {
	position: relative;
	width: 80%;
	font-size: .9rem;
	left: 3rem;
	color: var(--vi-yellow);
}
.line {
	position: relative;
	top: 9px;
	left: 0px;
	width: 40px;
	height: 2px;
	background-color: var(--vi-yellow);
}
h2 {
	font-weight: 800;
	font-size: 2.2rem;
	margin: 0.5rem 0;
}
/* MODAL */

.modal {
  display: none;
  position: fixed;
  z-index: 100;
  padding-top: 7rem;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  overflow: auto;
  background-color: var(--vi-dark-transparent);

}
.active {
	display: block;
}
.modal-content {
  background-color: var(--vi-light-dark);
  margin: auto;
  padding: 20px;
  width: 600px;
	border-radius: 1rem;
}

.close {
  color: var(--vi-yellow);
	font-size: 2rem;
  font-weight: bold;
}

.close:hover,
.close:focus {
  color: #000;
  text-decoration: none;
  cursor: pointer;
}
.top-row {
	display: flex;
	justify-content: space-between;
	align-items: center;
}
.project-name {
	font-size: 1.5rem;
	font-weight: 800;
}
.project-image {
	width: 100%;
	margin-top: 1rem;
}
.project-image img {
	object-fit: cover;
	width: 100%;
	height: 100%;
}
.description {
	margin-top: .5rem;
	text-align: left;
	font-size: .9rem;
	line-height: 1.3;
}
.project-links {
	margin-top: 1rem;
	display: flex;
	gap: 1rem;
}
.link a {
	display: block;
	width: 100%;
	height: 100%;
	text-decoration: none;
	color: var(--vi-yellow);
	font-weight: 800;
	font-size: 1rem;
}
.link {
	width: 7rem;
	padding: 5px 0;
	margin-top: 1rem;
	border-radius: .8rem;
	font-weight: 600;
	font-size: 1.1rem;
	color: var(--vi-yellow);
	border: 1px solid var(--vi-yellow);
	background-color: var(--vi-light-dark);
	transition: all .5s;
}
.link:hover,
.link:focus {
	cursor: pointer;
	color: var(--vi-dark);
	background-color: var(--vi-yellow);
  animation: pulse 1s;
  box-shadow: 0 0 0 .8rem transparent;
}
.link:hover>a,
.link:focus>a {
	color: var(--vi-dark);
}
.btnHolder {
	margin-top: 2rem;
	margin-bottom: 2rem;
}
@media only screen and (max-width: 1050px) {
	.image {
		width: 48%;
		height: 20rem;
	}

}

@media only screen and (max-width: 800px) {
	.wrapper {
		width: 90%;
	}
	.project-wrapper {
		flex-direction: column;
		align-items: center;
	}
	.image {
		cursor: pointer;
		width: 100%;
		height: 24rem;
		border-radius: 1rem;
		overflow: hidden;
		transition: all .3s;
	}
	.modal {
		padding-top: 3rem;
	}
}
@media only screen and (max-width: 600px) {
	.modal-content {
		width: 400px;
	}
}
@media only screen and (max-width: 400px) {
	.modal-content {
		width: 300px;
	}
}

</style>