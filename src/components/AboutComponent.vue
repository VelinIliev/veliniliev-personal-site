<template>
	<div class="wrapper">
		<div class="left-side">
			<img src="/images/21be7acb-b749-45cc-989f-4bb867686444.png">
		</div>
		<div class="right-side">
			<div class="line"></div>
			<div class="biography">
				Biography
			</div>
			<h2>About Me</h2>
			<p class="description">
				Full-Stack Developer with a creative background in Graphic Design.
				Strong foundation in front end and back end development, combined with a keen eye for design aesthetics.
				Eager to contribute unique insights and skills to dynamic development projects.
			</p>
			<p class="description">
				Strong passion for staying updated with the latest web development trends and technologies.
				Excellent problem-solving skills and the ability to collaborate effectively within a team.
				Strong communication skills in both technical and non-technical contexts.
			</p>
			<a href="/resume/VelinIliev-resume.pdf" download class="btn resume">Download Resume</a>
		</div>
	</div>
</template>

<script setup>

</script>

<style scoped>
.left-side {
	width: 40%;
	min-height: 500px;
	overflow: hidden;
	border-radius: 10px 0 0 10px ;
}
.left-side img {
	width: 100%;
	height: 100%;
	object-fit: cover;
}
.right-side {
	display: flex;
	flex-direction: column;
	width: 60%;
	background-color: var(--vi-light-dark);
	text-align: left;
	padding: 1.5rem 2rem;
}
.biography {
	position: relative;
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
.description {
	line-height: 1.3;
}
a.btn {
	text-align: center;
	text-decoration: none;
}
.resume {
	width: 12rem;
	letter-spacing: 0;
}
</style>