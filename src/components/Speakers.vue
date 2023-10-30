<script>
	import SwiperCore from 'swiper';
	import { Navigation } from 'swiper/modules';
	import { Swiper, SwiperSlide } from 'swiper/vue';
	import 'swiper/css';
	import 'swiper/css/navigation';

	SwiperCore.use([ Navigation ])

	export default {
		data() {
			return {
				swiperOptions: {
					breakpoints: {
						320: {
							slidesPerView: 1.46,
							spaceBetween: 10
						},
						771: {
							slidesPerView: 3.22,
							spaceBetween: 20
						}
					},

					navigation: {
						prevEl: '.speakers__swiper-button-prev',
						nextEl: '.speakers__swiper-button-next',
					}
				},

				speakers: [
					{
						authorName: 'Станислав',
						authorSurname: 'Орехов',
						authorPosition: 'Дизайнер, визуализатор, руководитель студии d-e-s-i-g-n.ru',
						authorImage: {
							image: '/images/speakers/speaker-orehov.jpg',
							webp: '/images/speakers/speaker-orehov.webp',
						}
					},
					{
						authorName: 'Светлана',
						authorSurname: 'Котлукова',
						authorPosition: 'Маркетолог, руководитель PR-агентства для дизайнеров «АрхДиалог»',
						authorImage: {
							image: '/images/speakers/speaker-kotlunova.jpg',
							webp: '/images/speakers/speaker-kotlunova.webp',
						}
					},
					{
						authorName: 'Максим',
						authorSurname: 'Вересов',
						authorPosition: 'Архитектор, строитель, руководитель компании деревянного строительства',
						authorImage: {
							image: '/images/speakers/speaker-veresov.jpg',
							webp: '/images/speakers/speaker-veresov.webp',
						}
					},
					{
						authorName: 'Андрей',
						authorSurname: '',
						authorPosition: 'Дизайнер, визуализатор, руководитель студии',
						authorImage: {
							image: '/images/speakers/speaker-andrey.jpg',
							webp: '/images/speakers/speaker-andrey.webp',
						}
					}
				],
			}
		},

		components: {
			Swiper,
			SwiperSlide,
		},
	}
</script>

<template>
	<section class="speakers">
		<h2 class="speakers__title">спикеры</h2>
		<swiper
		:breakpoints="swiperOptions.breakpoints"
		:navigation="swiperOptions.navigation"
		class="speakers__swiper swiper">
			<swiper-slide v-for="(speaker, index) in speakers" :key="index" class="speakers__swiper-slide swiper-slide">
				<figure class="speakers__swiper-slide-figure">
					<picture>
						<source :srcset="speaker?.authorImage?.webp" type="image/webp">
						<img class="speakers__swiper-slide-figure-image" :src="speaker?.authorImage?.image" width="380" height="380" :alt="speaker?.authorName + ' ' + speaker?.authorSurname" loading="lazy">
					</picture>
					<figcaption class="speakers__swiper-slide-figcaption">
						<p class="speakers__swiper-slide-figcaption-speaker">{{ speaker?.authorName }} <span class="speakers__swiper-slide-figcaption-speaker-highlight">{{ speaker?.authorSurname }}</span></p>
						<p class="speakers__swiper-slide-figcaption-position">{{ speaker?.authorPosition }}</p>
					</figcaption>
				</figure>
			</swiper-slide>
		</swiper>
		<div class="speakers__swiper-buttons">
			<div class="speakers__swiper-button-prev swiper__button-prev">
				<svg class="speakers__swiper-button-prev-icon" width="43" height="43" viewBox="0 0 43 43" fill="none" xmlns="http://www.w3.org/2000/svg">
					<rect x="43" y="43" width="43" height="43" transform="rotate(-180 43 43)" fill="#ffffff"/>
					<path d="M20 27L13.7585 20.9506L20 14.9011" stroke="#DA353B" stroke-width="1.5"/>
					<path d="M29 20.75H14.5" stroke="#DA353B" stroke-width="1.5" stroke-linejoin="round"/>
				</svg>
			</div>
			<div class="speakers__swiper-button-next swiper__button-next">
				<svg class="speakers__swiper-button-next-icon" width="43" height="43" viewBox="0 0 43 43" fill="none" xmlns="http://www.w3.org/2000/svg">
					<rect width="43" height="43" fill="#ffffff"/>
					<path d="M23 16L29.2415 22.0494L23 28.0989" stroke="#DA353B" stroke-width="1.5"/>
					<path d="M14 22.25H28.5" stroke="#DA353B" stroke-width="1.5" stroke-linejoin="round"/>
				</svg>
			</div>
		</div>
	</section>
</template>

<style scoped lang="scss">

@import "../style.scss";

.speakers {
	padding: 201px 0 80px;
	margin: 0 0 0 90px;
	@include mobile {
		padding: 0;
		margin: 0 0 0 13px;
	}
}

.speakers__title {
	font-family: 'HelveticaNeueCyr Black', 'Arial', sans-serif;
	font-size: 48px;
	font-weight: 900;
	line-height: 150%;
	text-transform: uppercase;
	position: relative;
	color: $text-color-2;
	margin: 0 0 63px 78px;
	@include mobile {
		letter-spacing: -3.5px;
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

.speakers__swiper {
	margin: 0 0 66px 78px;
	@include mobile {
		margin: 0 0 40px;
	}
}

.speakers__swiper-wrapper {

}

.speakers__swiper-slide {

}

.speakers__swiper-slide-figure {
	display: grid;
	gap: 27px 0;
	margin: 0;
	@include mobile {
		gap: 11px 0;
	}
}

.speakers__swiper-slide-figure-image {
	width: 100%;
	height: auto;
	aspect-ratio: 1;
	object-fit: cover;
}

.speakers__swiper-slide-figcaption {
	display: flex;
	flex-flow: column;

}

.speakers__swiper-slide-figcaption-speaker {
	font-family: 'Helvetica Bold', 'Arial', sans-serif;
	font-size: 24px;
	font-weight: 700;
	line-height: 140%;
	text-wrap: balance;
	text-transform: uppercase;
	color: $text-color-2;
	margin: 0 0 2px;
	@include mobile {
		line-height: 115%;
	}
}

.speakers__swiper-slide-figcaption-speaker-highlight {
	color: $special-color;
}

.speakers__swiper-slide-figcaption-position {
	color: $text-color-2;
	margin: 0;
}

.speakers__swiper-buttons {
	display: flex;
	justify-content: flex-end;
	align-items: center;
	gap: 0 20px;
	margin: 0 90px 0 auto;
	@include mobile {
		display: none;
	}
}

.speakers__swiper-button-prev {
	width: 43px;
	height: auto;
	aspect-ratio: 1;
	display: flex;
	justify-content: center;
	align-items: center;
	color: $text-color-1;
	border: 2px solid $special-color;
	box-sizing: border-box;
	cursor: pointer;
}

.speakers__swiper-button-prev-icon {
	width: 100%;
	height: 100%;
	display: block;
	color: $text-color-1;
}

.speakers__swiper-button-prev path {
	transition-property: stroke;
	transition-duration: 300ms;
	transition-timing-function: ease-in-out;
}

.speakers__swiper-button-prev:hover path {
	stroke: $text-color-1;
}

.speakers__swiper-button-prev rect {
	transition-property: fill;
	transition-duration: 300ms;
	transition-timing-function: ease-in-out;
}

.speakers__swiper-button-prev:hover rect {
	fill: $special-color;
}

.speakers__swiper-button-next {
	width: 43px;
	height: auto;
	aspect-ratio: 1;
	display: flex;
	justify-content: center;
	align-items: center;
	color: $text-color-1;
	border: 2px solid $special-color;
	box-sizing: border-box;
	cursor: pointer;
}

.speakers__swiper-button-next-icon {
	width: 100%;
	height: 100%;
	display: block;
	color: $text-color-1;
}

.speakers__swiper-button-next path {
	transition-property: stroke;
	transition-duration: 300ms;
	transition-timing-function: ease-in-out;
}

.speakers__swiper-button-next:hover path {
	stroke: $text-color-1;
}

.speakers__swiper-button-next rect {
	transition-property: fill;
	transition-duration: 300ms;
	transition-timing-function: ease-in-out;
}

.speakers__swiper-button-next:hover rect {
	fill: $special-color;
}
</style>
