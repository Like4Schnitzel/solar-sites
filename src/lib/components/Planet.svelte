<script lang="ts">
    export let url: string;
    export let fallbackImage: string;
    export let fbImgAlt: string;
    export let size: string;
    export let displayEmbed = true;
    export let rotationSpeed: number = 1;
    export let gradientTurnTime: string = "0s";
    let turnValue = -0.15;
    let gradient = `linear-gradient(${turnValue}turn, rgba(255, 255, 255, 0.5), rgba(0, 0, 0, 0.75))`
</script>

<div class="container" style="--size: {size}; --gradient: {gradient}; --rotation-speed: {20/rotationSpeed}s; --gradient-turn-time: {gradientTurnTime};">
    <a href={url}>
        <img src={fallbackImage} alt={fbImgAlt}/>
        <img src={fallbackImage} alt={fbImgAlt} class="overflow"/>
        {#if displayEmbed}
            <embed src={url} />
            <embed src={url} class="overflow"/>
        {/if}
        <div class="gradient"></div>
    </a>
</div>

<style>
    @keyframes move-element {
        0% {
            transform: translate(0px, 0px);
        }
        100% {
            transform: translate(100%, 0px);
        }
    }

    .container {
        display: block;
        position: relative;
        aspect-ratio: 1 / 1;
        width: var(--size);
        margin: 0;
        clip-path: circle();
    }

    .container a {
        pointer-events: auto;
    }

    .container embed {
        pointer-events: none;
    }

    .container embed,
    .container img {
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        width: 200%;
        height: 100%;
        animation: move-element var(--rotation-speed) linear infinite;
    }

    .container .overflow {
        left: -200%;
        margin-left: 1px;
    }

    .container .gradient {
        position: absolute;
        background-size: cover;
        width: 100%;
        height: 100%;
        background-image: var(--gradient);
        animation: mO var(--gradient-turn-time) linear 0s infinite
    }

    @keyframes mO {
        0% { transform: rotate(-45deg);   }
        100% { transform: rotate(315deg); }
    }
</style>
