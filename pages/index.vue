
<template>
	<main class="layout">
		<score-section :scores="data.scores" />
		<chart-section :chart="data.issuance" />
		<table-section :blocks="data.blocks" :events="data.events" :extrinsics="data.extrinsics" :transfers="data.transfers" />
	</main>
</template>

<script>
import ChartSection from '../sections/home/ChartSection.vue'
import ScoreSection from '../sections/home/ScoreSection.vue'
import TableSection from '../sections/home/TableSection.vue'

export default {
	name: 'IndexPage',
	layout: 'AuthLayout',
	components: { ScoreSection, ChartSection, TableSection },
	async asyncData({ $content }) {
		const data = await $content('home').fetch()
		return { data }
	},
}
</script>

<style lang="scss" scoped>
</style>

