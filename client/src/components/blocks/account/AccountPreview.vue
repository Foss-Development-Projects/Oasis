<script lang="ts" setup>

</script>

<template>
	<div class="account-preview">
		<router-view></router-view>
	</div>
</template>

<style lang="scss">
	@use './../../../assets/styles/modules/scrollbar' as scrl;
	.account-preview {
		height: calc(100vh - 1px);
		overflow: hidden;
		overflow-y: scroll;
		padding: 5px;
		border-left: 1px solid black;
		@include scrl.scrollbar(5px, var(--default-fg-color), var(--accent-color-1), 0px);
		background-color: var(--default-bg-color);
	}
</style>