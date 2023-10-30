<script setup>

</script>

<template>
	<section class="experience">
		<h2 class="experience__title"><span class="experience__title-highlight">Опыт</span> практиков</h2>
		<p class="experience__text">Узнайте, как эффективно работать и зарабатывать в сфере дизайна, визуализации, проектирования и строительства</p>
	</section>
</template>

<style scoped lang="scss">

@import "../style.scss";

.experience {
	padding: 58px 0 80px;
	margin: 0 0 0 90px;
	@include mobile {
		padding: 0;
		margin: 26px 29px 40px 27px;
	}
}

.experience__title {
	font-family: 'HelveticaNeueCyr Black', 'Arial', sans-serif;
	font-size: 48px;
	font-weight: 900;
	line-height: 150%;
	text-transform: uppercase;
	position: relative;
	color: $text-color-2;
	margin: 0 0 51px 78px;
	@include mobile {
		line-height: 91%;
		letter-spacing: -4px;
		margin: 0 0 12px;
	}
	&::before {
		content: '';
		width: 220px;
		height: auto;
		aspect-ratio: 1;
		position: absolute;
		top: -121px;
		left: -78px;
		background: transparent;
		border: 6px solid $special-color;
		@include mobile {
			content: none;
		}
	}
}

.experience__title-highlight {
	font-family: 'HelveticaNeueCyr Black', 'Arial', sans-serif;
	font-weight: 900;
	color: $special-color;
}

.experience__text {
	width: min(100%, 564px);
	font-family: 'Helvetica Light', 'Arial', sans-serif;
	font-size: 24px;
	font-weight: 300;
	line-height: 150%;
	text-wrap: balance;
	color: $text-color-2;
	margin: 0 0 0 78px;
	@include mobile {
		font-size: 18px;
		margin: 0;
	}
}
</style>
