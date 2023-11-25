<script lang="ts">
    export let url: string;
    export let fallbackImage: string;
    export let fbImgAlt: string;
    export let size: string;
    export let displayEmbed = true;
    let turnValue = 0.75;
    let gradient = `linear-gradient(${turnValue}turn, rgba(255, 255, 255, 1), 30%, rgba(0, 0, 0, 0))`
</script>

<div class="container" style="--size: {size}; --gradient: {gradient};">
    <a href={url}>
        <img src={fallbackImage} alt={fbImgAlt}/>
        {#if displayEmbed}
            <embed src={url} />
        {/if}
        <div class="gradient"></div>
    </a>
</div>

<style>
    .container {
        display: block;
        position: relative;
        aspect-ratio: 1 / 1;
        width: var(--size);
        margin: 0;
        border-radius: 50%;
    }

    .container embed {
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        width: 100%;
        height: 100%;
        pointer-events: none;
        border-radius: 50%;
        z-index: 1;
    }

    .container img {
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        width: 100%;
        height: 100%;
        border-radius: 50%;
        z-index: 1;
    }

    .container .gradient {
        position: absolute;
        background-size: cover;
        width: 100%;
        height: 100%;
        border-radius: 50%;
        background-image: var(--gradient);
        z-index: 2;
    }
</style>
