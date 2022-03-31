
<template>
	<p>
		<em>{{ score.title }}</em>
		<strong>{{ score.count }}</strong>
	</p>
</template>

<script>
export default {
	props: ['score']
}
</script>

<style lang="scss" scoped>

	@use '/assets/scss/polkadot/variables/colors/colors.scss' as COLOR;
	@use '/assets/scss/polkadot/variables/fonts/families.scss' as FONT;

	p
	{
		em
		{
			font-weight: 500;
			text-transform: uppercase;
			white-space: nowrap;
			margin: 0;
			display: block;
			font-style: normal;
			color: COLOR.$fourthB;
	
			&::before
			{
				content: "";
				display: inline-block;
				width: 0.8em;
				height: 0.8em;
				margin-right: 0.8em;
				border: 0.2em solid COLOR.$fifth;
				transform: rotate(25deg);
			}
		}
	
		strong
		{
			color: COLOR.$fifth;
			font-size: 1.4em;
			margin-left: 1.2em;
			font-weight: normal;
			font-family: FONT.$secondary;
		}
	}

</style>

