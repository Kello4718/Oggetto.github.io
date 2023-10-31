<script>

import { useVuelidate } from '@vuelidate/core'
import { required, email, minLength, sameAs } from '@vuelidate/validators'

export default {

	data() {
		return {
			v$: useVuelidate(),
			fio: '',
			company: '',
			email: '',
			phone: '',
		}
	},

	validations: {
		fio: {
			required
		},

		company: {
			required
		},

		email: {
			required,
			email
		},

		phone: {
			required
		}
	}
}
</script>

<template>
	<section class="registration" id="registration">
		<form class="registration__form" action="">
			<h2 class="registration__title"><span class="registration__title-highlight">принять</span> участие</h2>
			<fieldset class="registration__fieldset">
				<input v-model.trim="fio"
				:class="{
					'registration__fieldset-input--focus': fio.length > 0
				}"
				class="registration__fieldset-input" type="text" required>
				<legend class="registration__fieldset-legend">Ваши имя и фамилия</legend>
			</fieldset>
			<fieldset class="registration__fieldset">
				<input v-model.trim="company"
				:class="{
					'registration__fieldset-input--focus': company.length > 0
				}"
				class="registration__fieldset-input" type="text" required>
				<legend class="registration__fieldset-legend">Компания</legend>
			</fieldset>
			<fieldset class="registration__fieldset">
				<input v-model.trim="email"
				:class="{
					'registration__fieldset-input--focus': email.length > 0
				}"
				class="registration__fieldset-input" type="text" required>
				<legend class="registration__fieldset-legend">E-mail</legend>
			</fieldset>
			<fieldset class="registration__fieldset">
				<input v-model.trim="phone"
				:class="{
					'registration__fieldset-input--focus': phone.length > 0
				}"
				class="registration__fieldset-input" type="text" required>
				<legend class="registration__fieldset-legend">Телефон</legend>
			</fieldset>
			<button class="registration__button" type="submit">Зарегистрироваться</button>
		</form>
	</section>
</template>

<style scoped lang="scss">

@import "../style.scss";

.registration {
	width: min(100%, 1290px);
	min-height: 790px;
	height: auto;
	background: url('/images/registration/registration-background.png') no-repeat right 0 / 784px 790px;
	padding: 0 20px;
	margin: 0 0 0 auto;
	@include mobile {
		min-height: auto;
		background: url('/images/registration/registration-background--mobile.png') no-repeat right 0 / cover;
		padding: 33px 28px 40px;
	}
}

.registration__form {
	width: min(100%, 540px);
	display: flex;
	flex-flow: column;
	gap: 0;
	margin: 0;
}

.registration__title {
	font-family: 'HelveticaNeueCyr Black', 'Arial', sans-serif;
	font-size: 45px;
	font-weight: 900;
	line-height: normal;
	letter-spacing: 1.9px;
	text-transform: uppercase;
	position: relative;
	color: $text-color-2;
	margin: 77px 0 60px;
	@include mobile {
		font-size: 44px;
		line-height: 94%;
		letter-spacing: 0;
		margin: 0 0 22px;
	}
}

.registration__title-highlight {
	color: $special-color;
}

.registration__fieldset {
	width: 100%;
	position: relative;
	border: none;
	padding: 0;
	margin: 0;
}

.registration__fieldset-input {
	width: 100%;
	height: 47px;
	font-family: 'Helvetica Bold', 'Arial', sans-serif;
	font-size: 20px;
	font-weight: 700;
	line-height: 130%;
	text-transform: uppercase;
	color: $text-color-2;
	background: transparent;
	border: none;
	border-bottom: 3px solid $text-color-2;
	padding: 0 0 18px 0;
	margin: 0 0 62px;
	&:focus {
		outline: none;
	}
	@include mobile {
		color: $text-color-2;
		padding: 4px 0 21px;
		margin: 0 0 23px;
	}
}

.registration__fieldset-legend {
	font-family: 'Helvetica Bold', 'Arial', sans-serif;
	font-size: 20px;
	font-weight: 700;
	line-height: 130%;
	position: absolute;
	top: 0;
	left: 0;
	color: $text-color-2;
	transition-property: translate, font-family, font-size;
	transition-duration: 300ms;
	transition-timing-function: linear;
	pointer-events: none;
	@include mobile {
		font-family: 'Helvetica Bold', 'Arial', sans-serif;
		font-size: 14px;
		position: initial;
		margin: 0 0 10px;
	}
}

.registration__fieldset-input--focus + .registration__fieldset-legend {
	font-family: 'Helvetica Light', 'Arial', sans-serif;
	font-size: 14px;
	font-weight: 300;
	line-height: 185.714%;
	translate: 0 -29px;
	@include mobile {
		font-family: 'Helvetica Bold', 'Arial', sans-serif;
		line-height: 130%;
		translate: 0;
	}
}


.registration__button {
	width: 100%;
	height: 60px;
	font-family: 'Helvetica Bold', 'Arial', sans-serif;
	font-size: 20px;
	font-weight: 700;
	line-height: 130%;
	letter-spacing: 2.4px;
	text-transform: uppercase;
	display: flex;
	justify-content: center;
	align-items: center;
	position: relative;
	z-index: 0;
	color: $text-color-1;
	background: $special-color;
	border: none;
	padding: 0;
	margin: 0;
	overflow: hidden;
	cursor: pointer;
	transition-property: background, translate;
	transition-duration: 300ms;
	transition-timing-function: ease-in-out;
	@include mobile {
		text-transform: uppercase;
		letter-spacing: 0.5px;
		margin: 19px 0 0 0;
	}
	@media (min-width: 1024px) {
		&:hover {
			background: black;
		}
		&::before {
			content: '';
			width: 100%;
			height: 100%;
			position: absolute;
			top: 0;
			left: 0;
			z-index: -1;
			translate: -100% 0;
			color: #ffffff;
			background: black;
			transition-property: translate;
			transition-duration: 300ms;
			transition-timing-function: ease-in-out;
		}
		&:hover::before {
			translate: 0 0;
			color: #ffffff;
			background: black;
		}
	}
}
</style>
