
<template>
	<dropdown tabindex="0" :link="link" :color="color" @click="click($event)" @blur="blur()">
		<i v-if="icon" :icon="icon"></i>
		{{ selected.name }}
		<ul>
			<li v-for="option in options" :key="option.id" @click="select(option)" :active="option.id == selected.id"><a href="#">{{ option.name }}</a></li>
		</ul>
	</dropdown>
</template>

<script>
export default {
	name: 'ControlSelect',
	props: ['color', 'options', 'value', 'icon', 'link'],
	data()
	{
		return { selected: this.value, focus: false }
	},
	methods:
	{
		click(e)
		{
			if(document.activeElement === e.target)
			{
				if(this.focus)
				{
					this.focus = !this.focus;
					e.target.blur();
				}
				else
				{
					this.focus = !this.focus;
				}
			}
		},
		blur()
		{
			if(this.focus)
				this.focus = false;
		},
		select(option)
		{
			this.selected = option;
		}
	}
}
</script>

<style lang="scss" scoped>
</style>

