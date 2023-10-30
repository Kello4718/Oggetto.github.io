<script setup>

</script>

<template>
	<section class="preview">
		<div class="preview__content">
			<h1 class="preview__content-title"><span class="preview__content-title-highlight">ДИЗАЙН</span><br> КОНФЕРЕНЦИЯ</h1>
			<p class="preview__content-text">Главное событие в дизайне и архитектуре</p>
			<a class="preview__content-button" href="#registration">принять участие</a>
		</div>
		<div class="preview__info">
			<span class="preview__info-date">7-9 апреля 2019</span>
			<span class="preview__info-text">Культурный центр «ЗИЛ»</span>
			<img class="preview__info-image" src="/images/preview/preview-logo.svg" width="140" height="62" alt="ЗИЛ Культурный центр" title="ЗИЛ Культурный центр">
		</div>
	</section>
</template>

<style scoped lang="scss">

@import "../style.scss";

.preview {
	width: 100%;
	min-height: 645px;
	height: auto;
	position: relative;
	background: url('/images/preview/preview-background.png') no-repeat center / cover;
	padding: 203px 0 0;
	@include mobile {
		min-height: 665px;
		background: url('/images/preview/preview-background--mobile.png') no-repeat center / cover;
		padding: 229px 0 0;
	}
}

.preview__content {
	width: max-content;
	margin: 0 0 0 11.81%;
	@include mobile {
		margin: 0 0 0 27px;
	}
}

.preview__content-title {
	font-family: 'HelveticaNeueCyr Regular', 'Arial', sans-serif;
	font-size: 82px;
	font-weight: 400;
	line-height: 110%;
	color: $text-color-1;
	margin: 0 0 10px;
	@include mobile {
		font-size: 45px;
		margin: 0;
	}
}

.preview__content-title-highlight {
	font-family: 'HelveticaNeueCyr Black', 'Arial', sans-serif;
	font-weight: 900;
	color: $special-color;
}

.preview__content-text {
	font-family: 'Helvetica Regular', 'Arial', sans-serif;
	font-weight: 400;
	color: $text-color-1;
	margin: 0 0 21px;
	@include mobile {
		width: 65%;
		margin: 0 0 15px;
	}
}

.preview__content-button {
	width: 140px;
	height: 40px;
	font-family: 'Helvetica Regular', 'Arial', sans-serif;
	font-size: 14px;
	font-weight: 400;
	line-height: 185.714%;
	display: flex;
	justify-content: center;
	align-items: center;
	position: relative;
	color: $text-color-1;
	background: transparent;
	border: 1px solid $text-color-1;
	padding: 0;
	margin: 0;
	overflow: hidden;
	@include mobile {
		width: 173px;
		height: 50px;
		letter-spacing: 2.5px;
	}
	@media (min-width: 1024px) {
		&::before {
			content: '';
			width: 140px;
			height: 40px;
			position: absolute;
			top: 0;
			left: 0;
			translate: -100% 0;
			background: $special-color;
			mix-blend-mode: color;
			transition-property: translate;
			transition-duration: 300ms;
			transition-timing-function: ease-in-out;
		}
		&:hover::before {
			mix-blend-mode: color;
			translate: 0 0;
			background: $special-color;
		}
	}

}
.preview__info {
	display: grid;
	grid-template-columns: 1fr 140px;
	grid-template-rows: max-content;
	gap: 0 68px;
	position: absolute;
	right: 0;
	bottom: 125px;
	background: $special-color;
	padding: 20px 44px 20.5px 30px;
	@include tablet {
		bottom: 75px;
	}
	@include mobile {
		grid-template-columns: 1fr;
		bottom: 79px;
		padding: 27px 49px 14px 31px;
	}
}

.preview__info-date {
	grid-column: 1 / 2;
	font-family: 'HelveticaNeueCyr Black', 'Arial', sans-serif;
	font-size: 22.93px;
	font-weight: 900;
	line-height: 132.444%;
	text-transform: uppercase;
	color: $text-color-1;
	@include mobile {
		letter-spacing: -0.5px;
	}
}

.preview__info-text {
	grid-column: 1 / 2;
	color: #FFF;
	font-family: 'HelveticaNeueCyr Regular', 'Arial', sans-serif;
	font-size: 14.724px;
	font-weight: 400;
	line-height: 216.667%;
	text-transform: uppercase;
	color: $text-color-1;
}

.preview__info-image {
	grid-column: 2 / 3;
	grid-row: 1 / 3;
	object-fit: contain;
	color: $text-color-1;
	@include mobile {
		width: 117px;
		height: 51px;
		position: absolute;
		top: -58px;
		right: 29px;
	}
}
</style>
