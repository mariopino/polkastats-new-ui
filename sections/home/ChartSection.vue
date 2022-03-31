
<template>
	<section class="chart">
		<header>
			<h1>Total Issuance</h1>
			<h2>Total issuance over the 30 days</h2>
		</header>
		<chart-line :data="chart.data" :labels="chart.labels" />
	</section>
</template>

<script>
import ChartLine from '../../components/charts/ChartLine.vue'
export default {
	components: { ChartLine },
	props: ['chart'],
	data() {
		return {
			chartData: {
				Books: 24,
				Magazine: 30,
				Newspapers: 10,
			},
		}
	},
}
</script>

<style lang="scss" scoped>
@use '/assets/scss/polkadot/variables/colors/colors.scss' as COLOR;

section
{
	text-align: center;
	background-color: rgba(COLOR.$third, 0.1);

	> header
	{
		text-align: center;
		margin: 2.4em;

		> h1
		{
			font-size: 3.2em;
			font-weight: 500;
		}

		> h2
		{
			font-size: 1.6em;
			font-weight: 500;
		}
	}

	> div
	{
		// font-size: 1rem;
		max-height: 25em;
		// max-height: 250px;
		margin: auto;
	}

}

</style>

