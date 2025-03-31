<svelte:head>
	<title>ShrvB</title>
	<meta name="description" content="Home page" />
</svelte:head>

<div class="outmost-box">
    <div class="main-flex">
        <!-- First main box mobile -->
        <div class="flexbox one">About</div>

        <!-- Second main box mobile -->
        <div class="flexbox two">
            <div class="box-two-first">

            </div>

            <div class="box-two-second">

            </div>
        </div>

        <!-- Third main box mobile -->
        <div class="flexbox three">hi</div>

        <!-- Fourth main box mobile -->
        <div class="flexbox four">hi</div>

        <!-- Fifth main box mobile -->
        <div class="flexbox five">hi</div>
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
        height: 85%;
        flex-direction: column;
        align-items: center;
        justify-content: space-around;
    }

    .flexbox {
        border: 1px #FFF solid;
        width: 80%;
        height: 16%;
    }
</style>