<script lang="ts">
	import '../app.css';
	let { children } = $props();
</script>

<main class="app">
    {@render children()}
</main>

<style>
    .app {
        height: 100%;
        width: 100%;
        position: relative;
    }
</style>