
<script lang="ts">
		let input = document.getElementById("search-box");
		export default {
		computed : {
			console: () => console,
			window: () => window,
		},
	}
</script>
<template>
	<section class="search-bar">
		<form autocomplete="off" action="" class="form">
				<input ref="search" id="search-box" class="search-box" type="text" name="search" placeholder="Search here..." />
				
			<button class="search-submit-btn" id="search-submit-btn" type="submit">
				<img class="search-icon" src="./../../assets/images/icons/vector/search.svg" alt="Search Icon">
			</button>
		</form>
	</section>
</template>

<style lang="scss" scoped>
	.search-bar {
		display: flex;
		justify-content: flex-end;
		align-items: center;
	}
	.form {
		width: 100%;
		display: grid;
		height: 36px;
		grid-template-columns: 1fr 32px;
		column-gap: 15px;
		align-items: center;
		justify-content: center;
		border-radius: 50px;
		max-width: 600px;
		background-color: var(--accent-color-1);
		box-shadow: 0px 0px 10px var(--accent-color-1);
	}

	.search-box {
		font-size: 16px;
		border: none;
		outline: none;
		height: inherit;
		width: 100%;
		font-family: "Roboto", sans-serif;
		color: white;
		background: transparent;
		background-color: transparent;
		margin-left: 10px;
		line-height: 100%;
		caret-color: white;
	}

	.search-submit-btn {
		outline: none;
		border: none;
		background: none;
		background-color: var(--accent-color-2);
		padding: 1.5px 0;
		width: 30px;
		height: 30px;
		border-radius: 50%;
		cursor: pointer;
		position: relative;

		.search-icon {
			color: white;
			width: calc(30px - 10px);
			height: calc(30px - 10px);
			position: absolute;
			top: 50%;
			left: 50%;
			transform: translate(-50%, -50%);
		}
	}

	.search-menu {
		color: white;
		list-style: none;
		display: grid;
		border-radius: 5px;
		grid-template-rows: 1fr;
		grid-gap: 5px;
		max-height: 300px;
		max-width: 300px;
		overflow-y: auto;
		background-color: blanchedalmond;
		padding: 10px 5px 10px 10px;

		&::-webkit-scrollbar {
			width: 5px;
		}

		li {
			font-size: 1.1em;
			height: 30px;
			background-color: deeppink;
			padding: 5px;
			border-radius: 5px;
			font-family: "Roboto", sans-serif;
		}
	}
</style>