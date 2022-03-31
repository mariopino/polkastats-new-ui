<template>
	<footer class="layout">
		<article>
			<div>
				<div>
					<h2>
						<span class="social" icon="facebook"></span>
						<span class="social" icon="instagram"></span>
						<span class="social" icon="twitter"></span>
					</h2>
					<h1>
						<a href="#">
							<span>
								<img src="/brand/logo.svg" alt="Brand Logo" height="40">
							</span>
							<img src="/brand/text.svg" alt="Brand Text" height="40">
						</a>
					</h1>
				</div>
			</div>
			<nav aria-labelledby="Secondary Menu">
				<ul>
					<li><a href="#">About Us</a></li>
					<li><a href="#">Privacy Policy</a></li>
					<li><a href="#">Conditions of Use</a></li>
				</ul>
			</nav>
		</article>
		<address>
			<p color="fourth">
				<span class="info" icon="name">@PolkaStats</span>
				<span class="info" icon="email">polkastats@protonmail.com</span>
				<span class="info" icon="key">12344 54543 565436 546</span>
			</p>
			<p color="primary">
				<img src="/brand/grant_badge.png" alt="FFFFF" height="64" />
			</p>
		</address>
	</footer>
</template>


<script>
export default {
	name: 'FooterFrame',
}
</script>

<style lang="scss" scoped>

@use '/assets/scss/polkadot/variables/colors/colors.scss' as COLOR;

footer
{
	overflow: hidden;
	color: COLOR.$fifth;
	background-color: rgba(COLOR.$fourth, 0.9);
	display: flex;

	> article
	{
		padding: 2em;
		flex-grow: 5;
		display: flex;
		flex-direction: column;
		
		> div
		{
			margin: auto 0;

			> div
			{
				position: relative;
				left: 50%;
				display: inline-block;
				text-align: center;

				h1
				{
					font-size: 1em;

					img
					{
						height: 4em;
					}
				}

				> h2
				{
					font-size: 1.2em;
					display: flex;
					justify-content: center;
					gap: 1em;
					margin: 1em;

					> [icon]
					{
						background-color: COLOR.$primary;
						border-radius: 50%;
						position: relative;
						width: 2.8em;
						height: 2.8em;

						&::before
						{
							position: absolute;
							top: 50%;
							left: 50%;
							transform: translate(-50%, -50%);
						}
					}
				}
			}
		}

		> nav
		{
			> ul
			{
				text-align: left;
				text-transform: none;
				font-weight: 500;
			}
		}
	}

	> address
	{
		margin: 0;
		flex-grow: 1;
		display: flex;
    	flex-direction: column;
		
		> p
		{
			display: flex;
			flex-direction: column;
			justify-content: center;
			
			text-align: center;
			padding: 1.4em 2em;
			margin: 0;

			&[color="primary"]
			{
				background-color: COLOR.$primary;
			}

			&[color="fourth"]
			{
				background-color: COLOR.$fourth;
			}

			[icon]
			{
				display: block;
				padding: 0.6em 0;
				text-align: left;

				&::before
				{
					display: block;
					margin-bottom: 0.4em;
				}
			}

			> img
			{
				align-self: center;
				height: 6.4em;
			}
		}
	}
}

</style>