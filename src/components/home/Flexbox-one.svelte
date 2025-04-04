<script>
	import { goto } from '$app/navigation';
	import { fade } from 'svelte/transition';
	import { sineInOut } from 'svelte/easing';

	let visible = false;

	async function navigate() {
		visible = true;
		await new Promise((resolve) => setTimeout(resolve, 150)); // Wait for 1 second
		goto('/work');
	}
</script>

<button onclick={navigate} class="flexbox one">
	<h1 class="work-title">Test and test</h1>
</button>

{#if visible}
	<div
		class="blur-div"
		transition:fade={{
			duration: 150,
			easing: sineInOut
		}}
	></div>
{/if}

<style>
	.blur-div {
		position: absolute;
		background-color: #fff;
		height: 100vh;
		width: 100vw;
		top: 0;
		left: 0;
	}

	h1 {
		font-family: 'Ubuntu Mono';
	}

	.flexbox {
		border: 1px #fff solid;
		background-color: transparent;
		color: #fff;
		border-radius: 20px;
		position: relative;
		grid-row: 1 / 1 span;
		grid-column: 1 / 5 span;
	}

	.one:active {
		transition: opacity 1500ms ease-out, transform 1500ms ease-in;
		opacity: 0;
		transform: scale(10) translateY(50px);
	}

	@keyframes autorun {
		from {
			transform: translateY(100%);
		} to {
			transform: translateY(-100%);
		}
	}
</style>
