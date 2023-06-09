<script setup lang="ts">
	import ThemeSwitchVue from './../modules/ThemeSwitch.vue';
	import SearchBar from './../modules/SearchBar.vue';
</script>

<template>
	<nav class="appbar">
		<header class="appbar-header">
			<img class="appbar-header-logo" src="./../../assets/images/logo/Oasis.svg" alt="Site Logo" loading="lazy" />
			<router-link class="appbar-header-title" to="/">Oasis</router-link>
		</header>
		<ThemeSwitchVue class="appbar-theme" />
		<SearchBar class="appbar-search" />
		<section class="appbar-profile-section">
			<router-link to="/account" class="appbar-profile-section-image">
				<img 
					class="appbar-profile-pic"
					src="https://cdn-icons-png.flaticon.com/512/3237/3237447.png"
					alt="User Profile Picture"
					loading="lazy"
				/>
			</router-link>
			
			<button class="appbar-widget-button">
				<img class="appbar-widget" src="./../../assets/images/icons/vector/widget.svg" alt="User Profile"
					loading="lazy">
			</button>
		</section>
		<ul class="appbar-list">
			<li class="appbar-list-item appbar-list-theme">
				<p class="appbar-list-item-theme-title">Appearance: </p>
				<ThemeSwitchVue />
			</li>
			<li class="appbar-list-item">
				<SearchBar class="appbar-list-search" />
			</li>
		</ul>
	</nav>
</template>

<style lang="scss" scoped>
	@use './../../assets/styles/modules/layout' as mix;
	.appbar {
		width: 100%;
		background-color: var(--default-bg-color);
		color: var(--default-fg-color);
		padding: 0 5px;
		display: grid;
		grid-template-areas:
			"appbar-header appbar-theme appbar-search appbar-profile appbar-widget";
		grid-template-columns: 150px 90px 1fr 100px;
		align-items: center;
	}

	.appbar-header {
		grid-area: appbar-header;
		display: flex;
		align-items: center;
		width: 100%;
	}

	.appbar-header-logo {
		max-width: 40px;
		max-height: 40px;
	}

	.appbar-header-title {
		color: inherit;
		font-size: 36px;
		font-family: "Montserrat Alternates", sans-serif;
		font-weight: lighter;
		letter-spacing: -2px;
		text-decoration: none;
	}

	.appbar-theme {
		grid-area: appbar-theme;
	}

	.appbar-search {
		grid-area: appbar-search;
	}

	.appbar-profile-section {
		grid-area: appbar-profile;
		display: flex;
		margin-left: 15px;
		justify-content: space-between;
		align-items: center;
		&-image {
			@include mix.add-flex;
			.appbar-profile-pic {
				max-width: 35px;
				max-height: 35px;
			}
		}
		
	}

	.appbar-widget-button {
		grid-area: appbar-widget;
		display: flex;
		margin: 0 0 0 5px;
		justify-content: center;
		align-items: center;
		border-radius: 50%;
		width: 40px;
		height: 40px;
		padding: 5px;
		transition: background-color, 200ms ease-in-out;
		&:hover {
			background-color: var(--default-fg-color);
			transition: background-color, 100ms ease-in-out;
		}
		.appbar-widget {
			width: 100%;
			height: 100%;
		}
	}

	.appbar-list {
		display: none;
		grid-area: appbar-list;
		padding: 10px;
		grid-row-gap: 10px;
	}

	.appbar-list-item {
		width: 100%;
		display: flex;
		padding: 5px;
		align-items: center;
		border-radius: 10px;
		justify-content: center;
		background-color: rgba(0,0,0,0.5);
	}
	.appbar-list-theme {
		padding: 10px;
		justify-content: space-between!important;
		.appbar-list-item-theme-title {
			font-weight: bold;
			font-size: 16px;
			color: white;
		}
	}
	.appbar-list-search {
		height: auto;
		width: 100%;
	}

	@media (max-width: 650px) {
		.appbar {
			justify-content: space-between;
			grid-template-areas:
				"appbar-header appbar-profile appbar-widget"
				"appbar-list appbar-list appbar-list"
			;
			grid-template-columns: 130px 1fr;
		}

		.appbar-profile-section {
			justify-content: flex-end;
		}

		.appbar-theme,
		.appbar-search {
			display: none;
		}

		.appbar-list {
			display:grid;
			padding: 2.5px;
			margin-bottom: 5px;
		}
	}
</style>