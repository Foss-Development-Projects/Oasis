<script lang="ts" setup>
	import { homeSidebarRoutes } from '@/data/home/routes/homeRoutes';
</script>

<template>
	<aside class="sidebar" id="sidebar">
		<header class="sidebar-header">
			<v-icon icon="mdi-close-circle-outline"></v-icon>
		</header>
		<ul class="sidebar-list">
			<li class="sidebar-list-item">
				<form action="" method="GET" class="sidebar-list-item-form">
					<fieldset>
						<legend>Budget</legend>
						<v-text-field prepend-inner-icon="mdi-currency-usd" label="Min" variant="solo"></v-text-field>
						<v-text-field prepend-inner-icon="mdi-currency-usd" label="Max" variant="solo"></v-text-field>
					</fieldset>
				</form>
			</li>
			<li class="sidebar-list-item" v-for="(item, index) in homeSidebarRoutes" :key="index">
				<a class="sidebar-list-item-link" :href="item.path">
					<v-icon class="sidebar-list-item-link-icon" :icon="item.icon"></v-icon>
					<p class="sidebar-list-item-link-title">{{ item.name }}</p>
				</a>
			</li>
		</ul>
	</aside>
</template>

<style lang="scss">
	@use './../../assets/styles/modules/scrollbar' as mix;

	.sidebar {
		width: 250px;
		background: var(--default-bg-color);
		color: var(--default-fg-color);
		z-index: 1;
	}
	.sidebar-header {
		text-align: right;
		padding: 10px;
		i {
			cursor: pointer;
			border-radius: 50%;
			font-size: 40px;
			transition: background-color, box-shadow, 200ms ease-in-out;
			&:hover {
				transition: background-color, box-shadow, 200ms ease-in-out;
				box-shadow: 0 0 10px white;
			}
		}
		
	}
	.sidebar-list {
		padding: 10px;
		display: flex;
		flex-direction: column;
		align-items: center;
		overflow: hidden;
		overflow-y: scroll;
		padding-bottom: 55px;
		width: 250px;
		height: calc(100vh - 61px);
		@include mix.scrollbar(5px, var(--default-fg-color), var(--accent-color-1), 5px);

		&-item {
			margin-bottom: 5px;
			width: 100%;

			&-link {
				display: grid;
				grid-template-columns: 24px 1fr;
				grid-gap: 5px;
				padding: 5px;
				align-items: center;
				color: inherit;
				text-decoration: none;
				width: 100%;
				border-radius: 5px;
				background-color: var(--default-bg-color);
				transition: background-color, color, 200ms ease-in-out;

				&:hover {
					background-color: var(--default-fg-color);
					color: var(--default-bg-color);
					transition: background-color, color, 200ms ease-in-out;
				}

				&-title {
					font-size: 20px;
					font-family: "Open Sans", sans-serif;
				}

				&-icon {}
			}
		}
	}
</style>