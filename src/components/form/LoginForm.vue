<script setup lang="ts">
import { ref } from 'vue'
import LoginFormInput from './LoginFormInput.vue'
const saveEmail = ref<boolean>(false)

const handleClick = () => {
	saveEmail.value = !saveEmail.value
}

const saveEmailID = crypto.randomUUID()
</script>

<template>
	<form action="">
		<LoginFormInput label="E-mail" required placeholder="codelandia@gmail.com" type="email" />
		<LoginFormInput label="Senha" required placeholder="*********" type="password" />
		<div class="radio-input">
			<div class="form-control">
				<label :for="saveEmailID">Lembre de mim </label>
				<input
					type="radio"
					:id="saveEmailID"
					name="saveEmail"
					:value="saveEmail"
					@click="handleClick"
					:checked="saveEmail"
				/>
			</div>
			<a href="" target="_blank" rel="noopener noreferrer">Esqueceu sua senha? </a>
		</div>
		<div class="btn-signin">
			<button class="btn-signin__email" type="submit">Entra</button>
			<button class="btn-signin__google" type="button">Ou faça login com o Google</button>
		</div>
	</form>
</template>

<style lang="scss">
@use 'sass:map';
@import '../../styles/variables';

form {
	display: flex;
	flex-direction: column;
	gap: 0.5rem;
	align-self: center;

	width: 347px;

	padding-block: 2rem;
	padding: 0.5rem;
}

.radio-input {
	display: flex;
	justify-content: space-between;

	widows: 100%;

	.form-control {
		display: flex;
		gap: 0.5rem;

		label {
			order: 1;
			width: fit-content;
		}

		input {
			order: 0;
			width: 1rem;
			margin-bottom: 0.5rem;
		}
	}
}

.btn-signin {
	display: flex;
	flex-direction: column;
	gap: 1rem;
	padding-top: 1rem;

	button {
		color: map-get($colors, 'dark', '30');

		padding-block: 1rem;

		border: none;
		border-radius: 5px;

		@include typography('button');
	}

	&__email {
		background-color: map-get($colors, 'system', 'success');
		padding-inline: 10rem;
	}

	&__google {
		position: relative;
		background-color: map-get($colors, 'dark', '10');
		width: 100%;

		padding-inline: 3rem;

		&::before {
			content: '';
			display: block;
			float: left;

			width: 20px;
			height: 20px;

			background-image: url('/assets/img/icon-google.png');
			background-size: contain;
			background-repeat: no-repeat;
		}
	}
}
</style>
