
<template>
  <div class="pkd">
    <header-frame />
	<content-frame />
    <footer-frame />
  </div>
</template>

<script>
import HeaderFrame from './auth/HeaderFrame.vue'
import ContentFrame from './auth/ContentFrame.vue'
import FooterFrame from './auth/FooterFrame.vue'

export default {
  name: 'AuthLayout',
  components: { HeaderFrame, ContentFrame, FooterFrame },
}
</script>

<style lang="scss" scoped>

div
{
	display: flex;
	flex-direction: column;
	justify-content: stretch;
	min-height: 100vh;

	> *
	{
		flex-grow: 1;
	}
}

</style>