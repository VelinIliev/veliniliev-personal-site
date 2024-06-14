<template>
	<nav-bar @updateValue="handleUpdateValue"></nav-bar>
	<Transition>
		<home-component
				v-if="receivedValue==='Home'"
				@updateValue="handleUpdateValue"
		></home-component>
	</Transition>
	<Transition>
		<about-component
				v-if="receivedValue==='About'"
				@updateValue="handleUpdateValue"
		></about-component>
	</Transition>
	<Transition>
		<resume-component
				v-if="receivedValue==='Resume'"
				@updateValue="handleUpdateValue"
		></resume-component>
	</Transition>

		<portfolio-component
				v-if="receivedValue==='Portfolio'"
		></portfolio-component>

	<Transition>
		<contact-component
				v-if="receivedValue==='Contact'"
				@updateValue="handleUpdateValue"
		></contact-component>
	</Transition>

</template>

<script setup>
import NavBar from './components/NavBar';
import HomeComponent from './components/HomeComponent';
import AboutComponent from './components/AboutComponent';
import ResumeComponent from './components/ResumeComponent';
import PortfolioComponent from './components/PortfolioComponent';
import ContactComponent from './components/ContactComponent';
import { ref } from 'vue';

const receivedValue = ref('Home');

function handleUpdateValue(value) {
  receivedValue.value = value;
}
</script>

<style>
:root {
	--vi-white: #FFFFFF;
	--vi-dark: #212529;
	--vi-yellow: #ffc107;
	--vi-light-dark: #343a40;
	--vi-dark-transparent: #212529CC;

}
#app {
	font-family: 'Poppins', sans-serif;
	font-size: 1rem;
	font-weight: 400;
	letter-spacing: 1px;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;

}
* {
	box-sizing: border-box;
}
body, html {
	height: 100%;
	background-color: var(--vi-dark);
	color: var(--vi-white);
	margin: 0;
	padding: 0;
}
.v-enter-active {
  transition: opacity 0.5s ease;
}
.v-enter-from  {
  opacity: 0;
}
.wrapper {
	margin: auto;
	display: flex;
	padding-top: 4rem;
	width: 80%;
	max-width: 1400px;
}
.btn {
	width: 9rem;
	padding: 15px 0;
	margin-top: 1rem;
	border-radius: 2rem;
	font-weight: 600;
	font-size: 1.1rem;
	color: var(--vi-yellow);
	border: 1px solid var(--vi-yellow);
	background-color: var(--vi-light-dark);
	transition: all .5s;
}
.btn:hover,
.btn:focus {
	cursor: pointer;
	color: var(--vi-dark);
	background-color: var(--vi-yellow);
  animation: pulse 1s;
  box-shadow: 0 0 0 1rem transparent;
}

@keyframes pulse {
  0% { box-shadow: 0 0 0 0 var(--vi-yellow); }
}
</style>
