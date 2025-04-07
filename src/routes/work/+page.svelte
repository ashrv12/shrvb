<main>
    <div class="test">
        <div class="box"></div>
        <div class="box"></div>
        <div class="box"></div>
        <div class="box"></div>
    </div>
</main>

<style>
    main {
        height: 100vh;
        width: 100vw;
        background: linear-gradient(#e66465, #9198e5);
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .test {
        height: 50%;
        width: 50%;
        border: 1px solid rgba(255,255,255,0.5);
        backdrop-filter: blur(5px);
        box-shadow: 0 25px 45px rgba(0,0,0,0.1);
		background: rgba(255, 255, 255, 0.1);
        border-bottom: 1px solid rgba(255, 255, 255, 0.3);
        border-right: 1px solid rgba(255, 255, 255, 0.3);
        position: relative;
        display: flex;
        justify-content: center;
        align-items: center;
        overflow: hidden;
    }

    .test .box:nth-child(even) {
        background-color: black;
    }

    .test .box:nth-child(odd) {
        background-color: cadetblue;
    }

    .box {
        height: 50%;
        width: 50%;
        border-radius: 20px;
        position: absolute;
        animation: slideleft 25s linear infinite;
        opacity: 0;
    }

    .box:nth-child(1) {
        animation-delay: calc(25s / 4 * (4 - 1) * -1);
        /* -7.5 */
    }

    .box:nth-child(2) {
        animation-delay: calc(25s / 4 * (4 - 2) * -1);
        /* -5.0 */
    }

    .box:nth-child(3) {
        animation-delay: calc(25s / 4 * (4 - 3) * -1);
        /* -2.5 */
    }

    .box:nth-child(4) {
        animation-delay: calc(25s / 4 * (4 - 4) * -1);
        /* 0.0 */
    }


    @keyframes slideleft {
        0%, 15% {
            transform: translateX(210%);
            opacity: 0;
            animation-timing-function: ease-in; /* Quick pop into frame */
        }
        25%, 40.625% {
            transform: translateX(0);
            opacity: 1;
            animation-timing-function: linear; /* Stay in place */
        }
        45% {
            transform: translateX(0);
            opacity: 1;
            animation-timing-function: ease-out; /* Quick pop out of frame */
        }
        55%, 100% {
            opacity: 0;
            transform: translateX(-210%);
        }
    }
</style>