
<template>
	<section class="scores">
		<header :active="active">
			<h1>
				<a href="#">
					<span>
						<img src="/brand/logo.svg" alt="Brand Logo" height="40">
					</span>
					<img src="/brand/text.svg" alt="Brand Text" height="40">
				</a>
			</h1>
		</header>
		<article>
			<header>
				<form>
					<p>
						<i icon="search"></i>
						<input type="text" placeholder="Search by Block, Number, Hash, Extrinsic..." />
					</p>
				</form>
			</header>
			<div>
				<score-component v-for="score in scores" :key="score.title" :score="score" />
			</div>
		</article>
	</section>
</template>

<script>
import ScoreComponent from '../../components/ScoreComponent.vue'
export default {
	components: { ScoreComponent },
	props: ['scores'],
	data()
	{
		return { active: true };
	},
	mounted()
	{
		window.addEventListener('scroll', this.scroll)
	},
	methods:
	{
		scroll()
		{
			this.active = window.scrollY <= 60;
		}
	}
}
</script>

<style lang="scss" scoped>

	@use '/assets/scss/polkadot/variables/colors/colors.scss' as COLOR;
	@use '/assets/scss/polkadot/variables/colors/gradients.scss' as GRADIENT;

	section
	{
		position: relative;
		background-image: url('assets/images/backgrounds/cubes.png');
		background-size: 100%;
		background-position: center;
		padding: 6.4em 12.8em 0 12.8em;

		&::before
		{
			content: "";
			position: absolute;
			top: 0;
			left: 0;
			width: 100%;
			height: 100%;
			background: GRADIENT.$third;
			opacity: 50%;
		}

		> header
		{
    		position: relative;
			z-index: 1;
			margin: 3.2em;
			text-align: center;
			opacity: 0;
			transform: translateY(-100%);
			transition: 0.5s linear;

			&[active]
			{
				opacity: 1;
				transform: translateY(0);
			}

			> h1
			{
				font-size: 1em;
				line-height: 0;

				img
				{
					height: 4em;
				}

				> a > span
				{
					display: inline-block;
					background-color: COLOR.$fourth;
					padding: 1.6em;
					margin-right: 0.5em;
				}
			}
		}

		> article
		{
			display: grid;
			gap: 2em;
			position: relative;
			z-index: 1;
			padding: 4em;

			> div,
			> header
			{
				position: relative;
				z-index: 3;
			}

			> div
			{
				display: grid;
				grid-template-columns: repeat(auto-fill, minmax(16em, 1fr));
				grid-gap: 3em;
	
				> p
				{
					margin: 0;
				}
			}

			&::before,
			&::after
			{
				content: '';
				position: absolute;
				top: 0;
				left: 0;
				z-index: 2;
				width: 100%;
				height: 100%;
				background-color: COLOR.$primary;
				opacity: 25%;
				border-radius: 1em 1em 0 0;
				backface-visibility: hidden;
			}

			&::before
			{
				filter: blur(2.5em);
				opacity: 40%;
				z-index: 1;
			}
		}
	}
	
</style>

