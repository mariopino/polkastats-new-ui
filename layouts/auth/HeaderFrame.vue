<template>
	<header class="layout" :active="active" :menu="menu">
		<h2>
			<a href="#" @click="toggleMenu()">
				<i icon="menu"></i>
			</a>
		</h2>
		<h1>
			<a href="#">
				<img src="/brand/full.svg" alt="Brand" height="24">
			</a>
		</h1>
		<strong>
			<a href="">
				<i icon="kusama" color="secondary"></i>
				KSM $123.968 (-0.78%)
			</a>
		</strong>
		<nav aria-labelledby="Principal Menu">
			<ul>
				<li><a href="#">Validator</a></li>
				<li><a href="#">Validators</a></li>
				<li><a href="#">How to Stake</a></li>
				<li>
					<control-select :link="true" color="fourth" :options="[ { id: 'Blockchain', name: 'Blockchain' }, { id: 'Blocks', name: 'Blocks' }, { id: 'Transfers', name: 'Transfers' }, { id: 'Extrinsics', name: 'Extrinsics' }, { id: 'Events', name: 'Events' } ]" :value="{ id: 'Kusama', name: 'Kusama' }" />
				</li>
				<li><a href="#">Accounts</a></li>
			</ul>
		</nav>
		<ul>
			<li>
				<control-select color="primary" icon="kusama" :options="[ { id: 'Kusama', name: 'Kusama' } ]" :value="{ id: 'Kusama', name: 'Kusama' }" />
			</li>
			<li>
				<control-select color="fourthB" :options="[ { id: 'EN', name: 'EN' }, { id: 'ES', name: 'ES' } ]" :value="{ id: 'EN', name: 'EN' }" />
			</li>
		</ul>
	</header>
</template>


<script>
import ControlSelect from '../../components/form/ControlSelect.vue'
export default {
	components: { ControlSelect },
	name: 'HeaderFrame',
	data()
	{
		return { active: false, menu: false };
	},
	mounted()
	{
		window.addEventListener('scroll', this.scroll)
	},
	methods:
	{
		scroll()
		{
			this.active = window.scrollY > 60;
		},
		toggleMenu()
		{
			this.menu = !this.menu;
		}
	}
}
</script>


<style lang="scss" scoped>

@use '/assets/scss/polkadot/variables/colors/colors.scss' as COLOR;
@use '/assets/scss/polkadot/variables/fonts/families.scss' as FONT;

header
{
	position: fixed;
	z-index: 10;
	top: 0;
	left: 0;
	display: flex;
	width: 100%;
	align-items: center;
	color: COLOR.$fifth;
	padding: 1.6em;
	transition: 0.2s ease-out;
	white-space: nowrap;
	gap: 2em;

	&[active]
	{
		// padding: 0.4em 1.6em;
		&:not([menu])
		{
			padding: 0.8em 1.6em;
		}
		
		background-color: COLOR.$fourth;
		transition: 0.2s ease-in;

		& > h1
		{
			opacity: 1;
			transition: none;
			transition: 0.2s ease-in;
		}
	}

	&[active],
	&[menu]
	{
		> strong::before
		{
			opacity: 0;
		}
	}

	> h2
	{
		display: none;
	}

	// FIX: El Logo no está completamente centrado verticalmente
	> h1
	{
		font-size: 1em;
		margin: 0;
		opacity: 0;
		transition: 0.2s ease-out;

		img
		{
			height: 2em;
		}
	}

	> strong
	{
		position: relative;
		font-family: FONT.$secondaryMono;
		font-weight: 500;

		&::before
		{
			content: '';
			position: absolute;
			top: 0;
			left: 0;
			width: 100%;
			height: 100%;
			background-color: COLOR.$fifth;
			opacity: 15%;
			filter: blur(0.5em) saturate(200%);
		}
	}

	> nav
	{
		flex: 1;
	}

	> ul
	{
		> li
		{
			margin: 0.4em;
		}
	}
}

</style>