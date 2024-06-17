<template>
	<div class="wrapper">
		<div class="left-side">
			<div class="test">
				<div class="line"></div>
				<div class="contact">
					Contact
				</div>
				<h2>Get in touch</h2>
				<h3>Location</h3>
				<p>
					Sofia, Bulgaria
				</p>
				<h3>Contact</h3>
					<div class="link">
						<a href="mailto:veliniliev@gmail.com" target="_blank">Email: veliniliev@gmail.com</a>
					</div>
				<div class="link">
					<a href="https://github.com/VelinIliev" target="_blank">GitHub: https://github.com/VelinIliev</a>
				</div>
			</div>
		</div>
		<div class="right-side">
			<div>
				<form @submit.prevent="sendEmail">
					<div>
						<label for="name">Your Name</label><br>
						<input type="text" v-model="emailData.name" required placeholder="Enter Your Name"/>
					</div>
					<div>
						<label for="from">Your Email:</label><br>
						<input type="email" v-model="emailData.from" required placeholder="Enter Your Email"/>
					</div>
					<div>
						<label for="subject">Subject:</label><br>
						<input type="text" v-model="emailData.subject" required placeholder="Enter Your Subject"/>
					</div>
					<div>
						<label for="message">Message:</label><br>
						<textarea v-model="emailData.message" required placeholder="Enter Your Message"></textarea>
					</div>
					<button type="submit" class="btn">Send Email</button>
				</form>
				<p v-if="responseMessage">{{ responseMessage }}</p>
			</div>
		</div>
	</div>
</template>

<script setup>
	import { ref } from 'vue';
import emailjs from 'emailjs-com';

const emailData = ref({
  from: '',
  subject: '',
  message: '',
	name: '',
});

const responseMessage = ref('');

async function sendEmail() {
  try {
    const serviceID = process.env.VUE_APP_EMAILJS_serviceID;
    const templateID = process.env.VUE_APP_EMAILJS_templateID;
    const userID = process.env.VUE_APP_EMAILJS_userID;

    const templateParams = {
      from_name: emailData.value.name,
			to_name: "Velin",
      subject: emailData.value.subject,
      message: `from: ${emailData.value.from}\n
      					name: ${emailData.value.name}\n
      					subject: ${emailData.value.subject}\n
      					message: ${emailData.value.message}`,
    };

    const response = await emailjs.send(serviceID, templateID, templateParams, userID);
		if (response.status === 200) {
			responseMessage.value = 'Email sent successfully!';
			emailData.value.from = '';
			emailData.value.subject = '';
			emailData.value.message = '';
			emailData.value.name = '';
		}
  } catch (error) {
    responseMessage.value = 'Error sending email';
    console.error(error);
  }

}
</script>

<style scoped>
.left-side {
	padding: 2rem;
	text-align: left;
	width: 50%;
	min-height: 500px;
	overflow: hidden;
	border-radius: 10px 0 0 10px ;
	background-color: var(--vi-light-dark);
}
.right-side {
	display: flex;
	flex-direction: column;
	width: 50%;
	color: var(--vi-white);
	text-align: left;
	padding: 1.5rem 2rem;
}

.contact {
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
	margin: 0.5rem 0 2rem 0;
}
h3 {
	color: var(--vi-yellow);
	margin-top: 2rem;
}
.link {
	cursor: pointer;
	margin-bottom: .7rem;
}
a {
	display: block;
	cursor: pointer;
	color: var(--vi-white);
	text-decoration: none;
	width: 100%;
	height: 100%;
}

a.btn {
	text-align: center;
	text-decoration: none;
}
input, textarea {
	width: 100%;
	height: 3rem;
	background-color: var(--vi-dark);
	border: none;
	font-size: 1rem;
	border-bottom: 3px solid var(--vi-light-dark);
	margin-bottom: 1rem;
	color: var(--vi-white);
}
textarea {
	height: 100px;
	margin-top: 1rem;
}
input:focus, textarea:focus {
	outline: none;

	border-bottom: 3px solid var(--vi-yellow);
}
label {
	font-weight: 800;
}
input:-webkit-autofill,
input:-webkit-autofill:hover,
input:-webkit-autofill:focus,
input:-webkit-autofill:active  {
  transition: background-color 6000s;
  -webkit-text-fill-color: var(--vi-white);
}

@media only screen and (max-width: 800px) {
	.wrapper {
		display: inline-flex;
		flex-direction: column;
	}
	.left-side, .right-side {
		width: 100%;
	}
	.left-side {
		border-radius: 0;
	}
	.right-side {
		background-color: var(--vi-dark);
		margin-top: -9rem;
	}
}
</style>