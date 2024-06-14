<template>
	<div class="wrapper">
		<div class="left-side">
			<div>
				<div class="line"></div>
				<div class="skill">Skill</div>
				<h2>Expertise</h2>
				<h3 class="title">Programing Languages:</h3>
				<p>Python <b>|</b> JavaScript <b>|</b> C#</p>
				<h3>Frameworks:</h3>
				<p>VueJS <b>|</b> React <b>|</b> FastApi <b>|</b> Django / Django REST <b>|</b> .NET Core</p>
				<h3>Databases:</h3>
				<p>PostgreSQL <b>|</b> MSSQL</p>
				<h3>Tools:</h3>
				<p>Git Version Control <b>|</b> PyCharm <b>|</b> Rider <b>|</b> Visual Studio Code <b>|</b> Postman <b>|</b> Docker <b>|</b> Notion <b>|</b> Jira</p>
				<h3>Design Tools:</h3>
				<p>Photoshop <b>|</b> Illustrator <b>|</b> InDesign <b>|</b> After Effects <b>|</b> Figma</p>
				<h3>Languages:</h3>
				<p>English <b>|</b> French <b>|</b> Russian</p>
			</div>
			<div>
				<div class="line"></div>
				<div class="skill">Skill</div>
				<h2>Experience</h2>
				<div class="module">
					<div class="module-left">
						<i class="fa-solid fa-briefcase"></i>
					</div>
					<div class="module-right">
						<p class="period">May 2024 - present</p>
						<h4>Full Stack Developer - Intern & Team Lead Academy 2 - SoftUni</h4>
						<p class="description">
							Migration of SULS (Software University Learning System) from .NET Framework 4.6.1, Entity Framework 6.1.3,
							ASP.NET MVC 5.2 to .NET 8, Entity Framework Core, ASP.NET Core MVC
						</p>
					</div>
				</div>
				<div class="module">
					<div class="module-left">
						<i class="fa-solid fa-briefcase"></i>
					</div>
					<div class="module-right">
						<p class="period">November 2023 - February 2024</p>
						<h4>Full Stack Developer - Intern & Team Lead Academy - SoftUni</h4>
						<p class="description">
							As an intern in SoftUni’s ‘Intern & Team Lead Academy,’ I am actively involved in the
							‘Kitchen Helper’ project. I am contributing to the development of an advanced recipe
							search system and front end. Our team is dedicated to enhancing filters for preparation time,
							complexity, nutrition, etc. We leverage technologies such as FastAPI, PostgreSQL, Alembic,
							SQLAlchemy, Uvicorn, Nginx, VueJS, Pinia, Axios, and Docker to ensure a cutting-edge
							and efficient solution.
						</p>
					</div>
				</div>
				<div class="module">
					<div class="module-left">
						<i class="fa-solid fa-briefcase"></i>
					</div>
					<div class="module-right">
						<p class="period">November 2021 - present</p>
						<h4>Graphic Designer</h4>
						<p class="description">
							In conjunction with my regular work responsibilities, I have been crafting web banners to fulfill
							the company’s requirements. Furthermore, I adeptly utilize Python and ExtendScript to develop
							scripts that seamlessly transform Excel files into meticulously prepared InDesign documents,
							optimized for printing purposes
						</p>
					</div>
				</div>
			</div>
			<div class="end">
				<div class="line"></div>
				<div class="skill">Skill</div>
				<h2>Education</h2>
				<div class="wrapper-education">
					<div class="module" v-for="item in data.reverse()" :key="item.index">
					<div class="module-left">
						<i class="fa-solid fa-graduation-cap"></i>
					</div>
					<div class="module-right">
						<p class="period">{{ item.period }}</p>
						<h4>{{ item.name }}</h4>
						<p class="description">
							<a :href="item.link" target="_blank">certificate </a>
						</p>
					</div>
				</div>
				</div>
				<a href="/resume/VelinIliev-resume.pdf" download class="btn resume">Download Resume</a>
			</div>
		</div>
	</div>
</template>

<script setup>
let data = [
	{
		period: "July 2022 - August 2022",
		name: "Programming Basics",
		link: "https://softuni.bg/certificates/details/140540/cdc98c99"
	},
	{
		period: "September 2022 - December 2022",
		name: "Programming Fundamentals",
		link: "https://softuni.bg/certificates/details/148794/32086962"
	},
	{
		period: "January 2023 - February 2023",
		name: "HTML & CSS",
		link: "https://softuni.bg/certificates/details/162904/6154e496"
	},
	{
		period: "January 2023 - February 2023",
		name: "Python Advanced",
		link: "https://softuni.bg/certificates/details/159314/afb9a3d3"
	},
	{
		period: "January 2023 - February 2023",
		name: "MSSQL",
		link: "https://softuni.bg/certificates/details/157955/30bb58a2"
	},
	{
		period: "March 2023 - April 2023",
		name: "Python OOP",
		link: "https://softuni.bg/certificates/details/168162/acb3f086"
	},
	{
		period: "March 2023 - April 2023",
		name: "JS front-end",
		link: "https://softuni.bg/certificates/details/170672/ad7e8ffb"
	},
	{
		period: "May 2023 - June 2023",
		name: "Python Web Basics (Django)",
		link: "https://softuni.bg/certificates/details/177840/0f00f69b"
	},
	{
		period: "July 2023 - August 2023",
		name: "Python Web Framework (Django)",
		link: "https://softuni.bg/certificates/details/182369/e4bb5d6e"
	},
	{
		period: "September 2023 - October 2023",
		name: "PostgreSQL",
		link: "https://softuni.bg/certificates/details/186015/5edba1e2"
	},
	{
		period: "November 2023 - December 2023",
		name: "Python ORM",
		link: "https://softuni.bg/certificates/details/193809/7a314e6e"
	},
	{
		period: "March 2024 - April 2024",
		name: "Software Engineering and DevOps",
		link: "https://softuni.bg/certificates/details/213389/9f709d59"
	},
]
console.log(data)
</script>

<style scoped>
.left-side {
	width: 90%;
	text-align: left;
	display: flex;
	flex-direction: column;
	gap: 2rem ;
}
.skill {
	position: relative;
	font-size: .9rem;
	left: 3rem;
	color: var(--vi-yellow);
}
.line {
	position: relative;
	top: 9px;
	left: 0;
	width: 40px;
	height: 2px;
	background-color: var(--vi-yellow);
}
h2 {
	font-weight: 800;
	font-size: 2.2rem;
	margin: 0.5rem 0;
}
h3 {
	color: var(--vi-yellow);
	margin-bottom: -.4rem;
}
.wrapper {
	width: 60%;
}
p {
	line-height: 1.3;
}
.module {
	display: flex;
}
.module-left {
	padding-top: 1.5rem;
	min-width: 2.6rem;
}
.module-left i {
	font-size: 1.5rem;
	color: #ffc107;
}
h4 {
	font-size: 1.2rem;
	margin-top: -.9rem;
	margin-bottom: -.5rem;
}
.period {
	color: var(--vi-yellow);
	font-size: .9rem;
}
.description {
	font-size: .9rem;
}
.end {
	margin-bottom: 2rem;
}
a {
	color: #ffc107;
	text-decoration: none
}
.wrapper-education {
	display: flex;
	flex-wrap: wrap;
	justify-content: space-between;
}
.wrapper-education>.module {
	width: 45%;
}
a.btn {
	display: block;
	text-align: center;
	text-decoration: none;
	margin-top: 3rem;
}
.resume {
	width: 14rem;
	letter-spacing: 0;
}
b {
	color: var(--vi-yellow);
}
</style>