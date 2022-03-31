<script>
import { Line } from 'vue-chartjs'
import COLOR from 'assets/scss/polkadot/variables/colors/colors.scss'; 
import FONT from 'assets/scss/polkadot/variables/fonts/families.scss'; 

export default {
	extends: Line,
	props: ['data', 'labels'],
	data()
	{
		return {
			gradient: null,
			gradient2: null,
			chartOptions:
			{
				responsive: true,
				maintainAspectRatio: false,
				legend:
				{
					display: false,
				},
				tooltips:
				{
					backgroundColor: COLOR.fourth,
					displayColors: false,
					titleFontColor: COLOR.primary,
					titleFontStyle: '700',
					titleFontSize: 14,
					titleFontFamily: FONT.secondary,
					titleMarginBottom: 4,
					titleSpacing: 0,
					bodyFontColor: COLOR.fifth,
					bodyFontFamily: FONT.secondary,
					bodyFontSize: 12,
					bodyFontStyle: 500,
					bodySpacing: 0,
					footerSpacing: 0,
					footerMarginTop: 0,
					yPadding: 6,
					xPadding: 8,
					cornerRadius: 3,
					caretSize: 6,
					caretPadding: 10,
				},
				scales:
				{
					xAxes:
					[
						{
							ticks:
							{
								beginAtZero: false,
								fontSize: 10,
								fontColor: COLOR.fourth,
								fontFamily: FONT.secondary,
								autoSkipPadding: 6,
								padding: 6,
							},
							gridLines:
							{
								display: true,
								color: COLOR.fourth + '80',
								lineWidth: 0.2,
								zeroLineWidth: 2,
								zeroLineBorderDash: [5, 5],
								zeroLineColor: COLOR.fourth,
							},
							scaleLabel:
							{
								display: true,
								labelString: 'BLOCK',
								fontSize: 16,
								fontStyle: '500',
								fontColor: COLOR.fourthB,
								fontFamily: FONT.primary,
								padding: 16,
							},
						},
					],
					yAxes:
					[
						{
							ticks:
							{
								suggestedMin: 0,
								fontColor: COLOR.fourth,
								autoSkipPadding: 12,
								padding: 6,
								fontSize: 10,
								fontFamily: FONT.secondary,
							},
							gridLines:
							{
								display: true,
								color: COLOR.fourth + '80',
								lineWidth: 0.2,
								zeroLineWidth: 2,
								zeroLineBorderDash: [5, 5],
								zeroLineColor: COLOR.fourth,
							},
							scaleLabel:
							{
								display: true,
								labelString: 'TOTAL ISSUANCE',
								fontSize: 16,
								fontStyle: '500',
								fontColor: COLOR.fourthB,
								fontFamily: FONT.primary,
								padding: 16,
							},
						},
					],
				},
			},
			loading: true,
			apiData: [],
		}
	},
	mounted()
	{
		this.renderChart(
			{
				labels: this.labels,
				datasets:
				[
					{
						borderColor: COLOR.secondary + '80',
						borderWidth: 1,
						pointBackgroundColor: 'transparent',
						pointBorderColor: 'transparent',
						hoverBackgroundColor: 'transparent',
						hoverBorderColor: COLOR.fourth,
						pointRadius: 6,
						pointStyle: 'rect',
						hoverBorderWidth: 3,
						hoverRadius: 6,
						tension: 0,
						backgroundColor: COLOR.secondary + '40',
						data: this.data,
					},
				],
			},
			this.chartOptions
		)
	},
}
</script>
