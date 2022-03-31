
<template>
  <section class="tables">
	  <table-component v-if="blocks" :items="blocks" color="primary">
		<template #cell(block)="data">
			<tag color="primary">{{ data.value }}</tag>
		</template>
		<template #cell(status)="data">
			<i icon="check" :color="data.value"></i>
		</template>
	  </table-component>
	  <table-component v-if="transfers" :items="transfers" color="fourth">
		<template #cell(hash)="data">
			<tag>{{ data.value }}</tag>
		</template>
		<template #cell(from)="data">
			<i icon="avatar">{{ data.value }}</i>
		</template>
		<template #cell(to)="data">
			<i icon="avatar">{{ data.value }}</i>
		</template>
	  </table-component>
	  <table-component v-if="extrinsics" :items="extrinsics">
		<template #cell(extrinsic)="data">
			<span v-for="value of data.value" :key="value">{{ value }}</span>
		</template>
	  </table-component>
	  <table-component v-if="events" :items="events">
		<template #cell(event)="data">
			<span v-for="value of data.value" :key="value">{{ value }}</span>
		</template>
	  </table-component>
  </section>
</template>

<script>
import TableComponent from '../../components/TableComponent.vue'
export default {
	components: { TableComponent },
	props: ['blocks', 'transfers', 'extrinsics', 'events'],
}
</script>

<style lang="scss" scoped>

	section
	{
		display: flex;
		flex-wrap: wrap;
		gap: 3.2em 6.4em;;

		> article
		{
			flex: 1 1 0;
		}
	}

</style>

