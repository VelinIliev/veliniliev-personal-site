<template>
	<div class="nav-wrapper">
		<ul>
			<li>
				<img src="logos/vi-logo.svg" class="logo" @click="emitValue('Home')" alt="logo">
			</li>
			<li @click="emitValue('Home')" :class="['link-element', currentValue==='Home' ? 'active' : '']">
				<div class="text">Home</div>
				<div><i class="fa-solid fa-house"></i></div>
			</li>
			<li @click="emitValue('About')" :class="['link-element', currentValue==='About' ? 'active' : '']">
				<div class="text">About</div>
				<div><i class="fa-solid fa-user"></i></div>
			</li>
			<li @click="emitValue('Resume')" :class="['link-element', currentValue==='Resume' ? 'active' : '']">
				<div class="text">Resume</div>
				<div><i class="fa-solid fa-file"></i></div>
			</li>
			<li @click="emitValue('Portfolio')" :class="['link-element', currentValue==='Portfolio' ? 'active' : '']">
				<div class="text">Portfolio</div>
				<div><i class="fa-solid fa-briefcase"></i></div>
			</li>
			<li @click="emitValue('Contact')" :class="['link-element', currentValue==='Contact' ? 'active' : '']">
				<div class="text">Contact</div>
				<div><i class="fa-solid fa-envelope"></i></div>
			</li>
		</ul>

	</div>

</template>

<script setup>
import {defineEmits, ref} from 'vue';
const emit = defineEmits(['updateValue']);
const currentValue = ref('')

function emitValue(value) {
  emit('updateValue', value);
	currentValue.value = value;
}
</script>

<style scoped>
.nav-wrapper {
	position: fixed;
	width: 5.5rem;
	height: 100%;
	z-index: 100;
}
.logo {
	padding: .5rem;
	cursor: pointer;
}
ul {
	list-style: none;
	padding: 0;
	margin: 0;
}
.link-element {
	position: relative;
	margin-top: 1rem;
	display: flex;
	align-items: center;
	justify-content: end;
	left: -70px;
	font-weight: 600;
	width: 140px;
	height: 55px;
	padding-right: 20px;
	background-color: var(--vi-light-dark);
	border-radius: 0 30px 30px 0;
	transition: all 1s ease-out;
}
.link-element i {
	color: var(--vi-yellow);
}
.text {
	display: none;
}
.link-element i {
	font-size: 1.2rem;
	margin-left: 10px;
}
.link-element:hover {
	cursor: pointer;
	left: 0;
}
.link-element:hover > div > i {
	transform: rotate(360deg);
	transition: all 1s ease-out;
}
.link-element:hover > .text {
	display: block;
	transition: all 1s;
}
.active {
	background-color: var(--vi-yellow);
}
.active i {
	color: var(--vi-dark);
}
.active .text {
	color: var(--vi-dark) ;
}
@media only screen and (max-width: 800px) {
	.nav-wrapper {
		position: fixed;
		bottom: 0;
		width: 100%;
		height: 3rem;
		background-color: var(--vi-yellow);
		z-index: 100;
	}
	.logo {
		display: none;
	}
	ul {
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		gap: 1rem;

	}
	.link-element {
		position: static;
		margin-top: 0rem;
		display: flex;
		align-items: center;
		justify-content: center;
		left: 0;
		font-weight: 600;
		width: 3rem;
		height: 3rem;
		padding-right: 0px;
		background-color: var(--vi-yellow);
		border-radius: 0;
		transition: all 0s;
	}
	.link-element i {
		margin-left: 0;
	}
	.link-element i {
		color: var(--vi-dark);
	}
	.link-element:hover > .text {
		display: none;
	}
	.active i {
		color: var(--vi-yellow) ;
	}
	.active {
		background-color: var(--vi-dark);
		padding-right: 0px;
	}
}


</style>