<script setup>

</script>

<template>
	<section class="experts">
		<div class="experts__info">
			<h2 class="experts__info-title">О чем <span class="experts__info-title-highlight">молчат</span> дизайн-эксперты?</h2>
			<p class="experts__info-text">Спикеры поделятся практическими знаниями, особенностями подхода, секретами и фишками.</p>
			<p class="experts__info-text">Каждый найдет свое.</p>
		</div>
		<picture class="experts__picture">
			<source srcset="/images/experts/expert.webp" type="image/webp">
			<img class="experts__image" src="/images/experts/expert.jpg" width="831" height="470" alt="Эксперт" loading="lazy">
		</picture>
	</section>
</template>

<style scoped lang="scss">

@import "../style.scss";

.experts {
	display: grid;
	grid-template-columns: 57.71% 29.03%;
	align-items: center;
	gap: 0 59px;
	@include mobile {
		grid-template-columns: 1fr;
		padding: 0 28px 0 0;
		margin: 0 0 36px;
	}
}

.experts__info {
	grid-column: 2 / 3;
	grid-row: 1 / 2;
	display: flex;
	flex-flow: column;
	gap: 16px 0;
	@include mobile {
		width: 268px;
		grid-column: 1 / 2;
		grid-row: 2 / 3;
		gap: 0;
		margin: -70px 0 0 28px;
	}
}

.experts__info-title {
	font-family: 'HelveticaNeueCyr Black', 'Arial', sans-serif;
	font-size: 36px;
	font-weight: 900;
	line-height: 110%;
	text-transform: uppercase;
	position: relative;
	color: $text-color-2;
	margin: 0;
	@include mobile {
		grid-column: 1 / 2;
		grid-row: auto;
		line-height: 102%;
		letter-spacing: 3.2px;
		margin: 0 0 15px;
	}
}

.experts__info-title-highlight {
	color: $special-color;
}

.experts__info-text {
	font-family: 'Helvetica Light', 'Arial', sans-serif;
	font-weight: 300;
	color: $text-color-2;
	margin: 0;
	@include mobile {
		margin: 0 0 5px;
	}
}

.experts__info-text + .experts__info-text {
	font-family: 'HelveticaNeueCyr Bold', 'Arial', sans-serif;
	font-weight: 900;
	color: $special-color;
	margin: 0;
}

.experts__picture {
	grid-column: 1 / 2;
	grid-row: 1 / 2;
}

.experts__image {
	width: 100%;
	min-height: 260px;
	height: auto;
	display: block;
	object-fit: cover;
}
</style>
