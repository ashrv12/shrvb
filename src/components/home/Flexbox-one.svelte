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
    <img class="kubelogo" src="kubernetes.svg" alt="Kubernetes Logo" />
	<h1 class="work-title">Kubernetes</h1>
    <div class="fuzzy"></div>
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
    .work-title{
        color: rgb(12, 12, 12);
        font-size: 3em;
        font-weight: 900;
    }

    h1 {
        font-family: 'Ubuntu Mono';
    }
    
	.blur-div {
		position: absolute;
		background-color: #fff;
		height: 100vh;
		width: 100vw;
		top: 0;
		left: 0;
	}

    .fuzzy {
        position: absolute;
        inset: -200%;
		opacity: 3%;
		z-index: 20;
		background-image: url("static.avif");
		animation: shift 0.5s linear infinite both;
		pointer-events: none;
    }

	.flexbox {
        /* Glassmorphism effects */
        border: 1px solid rgba(255,255,255,0.5);
        backdrop-filter: blur(5px);
        box-shadow: 0 25px 45px rgba(0,0,0,0.1);
		background: rgba(255, 255, 255, 0.1);
        /* Normal css */

        overflow: hidden;
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 1em;
		color: #fff;
		border-radius: 20px;
		position: relative;
		grid-row: 1 / 1 span;
		grid-column: 1 / 5 span;
	}

    .kubelogo {
        height: 5em;
        width: auto;
        -webkit-animation: rotating 2s linear infinite;
        -moz-animation: rotating 2s linear infinite;
        -ms-animation: rotating 2s linear infinite;
        -o-animation: rotating 2s linear infinite;
        animation: rotating 10s linear infinite;
    }

	.one:active {
		transition: opacity 1500ms, transform 1500ms;
		opacity: 0;
		transform: scale(10) translateY(50px);
	}

	@keyframes rotating {
		from {
            -ms-transform: rotate(0deg);
            -moz-transform: rotate(0deg);
            -webkit-transform: rotate(0deg);
            -o-transform: rotate(0deg);
			transform: rotate(0deg);
		} to {
            -ms-transform: rotate(360deg);
            -moz-transform: rotate(360deg);
            -webkit-transform: rotate(360deg);
            -o-transform: rotate(360deg);   
			transform: rotate(360deg);
		}
	}

	@keyframes shift {
		0% {
			transform: translateX(10%) translateY(10%);
		} 100% {
			transform: translateX(-10%) translateY(-10%);
		}
	}
</style>
