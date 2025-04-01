<script>
    import FlexboxFour from "../components/home/Flexbox-four.svelte";
	import FlexboxOne from "../components/home/Flexbox-one.svelte";
    import FlexboxThree from "../components/home/Flexbox-three.svelte";
    import FlexboxTwo from "../components/home/Flexbox-two.svelte";

</script>
<svelte:head>
	<title>ShrvB</title>
	<meta name="description" content="Home page" />
</svelte:head>

<div class="outmost-box">
    <div class="main-flex">
        <!-- First main box mobile -->
        <FlexboxOne />

        <!-- Second main box mobile -->
        <FlexboxTwo />

        <!-- Third main box mobile -->
        <FlexboxThree />

        <!-- Fourth main box mobile -->
        <FlexboxFour />

    </div>
</div>

<style>
    .outmost-box {
        display: flex;
        align-items: center;
        justify-content: center;
        height: 100vh;
        width: 100vw;
    }

    .main-flex {
        display: flex;
        width: 100%;
        height: 70%;
        flex-direction: column;
        align-items: center;
        justify-content: space-around;
    }
</style>