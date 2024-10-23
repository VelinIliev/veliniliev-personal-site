<template>
	<div class="wrapper">
		<div class="left-side">
			<div class="line"></div>
			<p class="antecedent">Hey, I am</p>
			<h1>Velin Iliev</h1>
			<p class="profession one">Full-Stack Developer</p>
			<p class="profession two">Graphic Designer</p>
			<p class="description">
				Full-Stack Developer and Graphic Designer with a unique blend of technical and creative skills.
				Proficient in both front and back end development, alongside a strong design background.
				Passionate about creating seamless user experiences and visually appealing interfaces.
				Committed to staying updated with the latest industry trends.</p>
			<button class="btn"  @click="emitValue('About')">About Me</button>
		</div>
		<div class="right-side">
			<img src="images/48b8646e-bd7f-484c-b145-34eae31d6f1e.png">
		</div>
	</div>
</template>

<script setup>
import { defineEmits } from 'vue';
const emit = defineEmits(['updateValue']);

function emitValue(value) {
  emit('updateValue', value);
}
</script>

<style scoped>
.left-side {
	display: flex;
	flex-direction: column;
	width: 60%;
	background-color: var(--vi-light-dark);
	border-radius: 10px 0 0 10px ;
	text-align: left;
	padding: 1.5rem 2rem;
}
.line {
	position: relative;
	top: 25px;
	left: -50px;
	width: 40px;
	height: 2px;
	background-color: var(--vi-yellow);
	border: 1px solid var(--vi-yellow);
}
h1 {
	font-size: 3rem;
	margin: 0px;
}
.profession {
	margin-top: 10px;
	font-weight: 800;
	font-size: 1.5rem;
	color: var(--vi-yellow);
}
.one {
	animation: animate-professions-one 6s 0s ease-in infinite;
}
.two {
	animation: animate-professions-two 6s 0s ease-in infinite;
}
@keyframes animate-professions-one {
	0% {display: none;transform-origin: top; transform: scaleY(0);opacity: 0;}
	1% { display: block; transform-origin: top; transform: scaleY(0);opacity: 0;}
	20% { transform-origin: top; transform: scaleY(1);opacity: 1;}
	40% { transform-origin: bottom; transform: scaleY(1);opacity: 1;}
	49% { transform-origin: bottom; transform: scaleY(0);opacity: 0;}
	50% { display: none}
	100% {display: none}
}
@keyframes animate-professions-two {
	0% { display: none}
	50% { display: none}
	51% { display: block; transform-origin: top; transform: scaleY(0);opacity: 0;}
	70% { transform-origin: top; transform: scaleY(1);opacity: 1;}
	90% { transform-origin: bottom; transform: scaleY(1);opacity: 1;}
	99% { transform-origin: bottom; transform: scaleY(0);opacity: 0;}
	100% {display: none; transform-origin: bottom; transform: scaleY(0);opacity: 0;}
}
.description {
	font-weight: 200;
	font-size: 1rem;
	margin-top: 0px;
	line-height: 1.5;
	margin-bottom: 10px;
}
.right-side {
	width: 40%;
	min-height: 500px;
	overflow: hidden;
}
.right-side img {
	width: 100%;
	height: 100%;
	object-fit: cover;
}
@media only screen and (max-width: 800px) {
	.wrapper {
		flex-direction: column-reverse;
		width: 90%;
	}
	.left-side {
		width: 100%;
		margin-top: -8rem;
		border-radius: 0;
	}
	.right-side {
		width: 100%;
		height: 10px;
	}
	.right-side img {
		width: 100%;
		height: 80%;
		object-fit: cover;
	}
}
</style>