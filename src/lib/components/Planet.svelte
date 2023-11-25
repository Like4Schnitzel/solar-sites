<script lang="ts">
    export let url: string;
    export let fallbackImage: string;
    export let fbImgAlt: string;
    export let size: string;
    export let displayEmbed = true;
</script>

<div class="container" style="--size: {size}">
    <a href={url}>
        <img src={fallbackImage} alt={fbImgAlt}/>
        {#if displayEmbed}
            <embed src={url} />
        {/if}
    </a>
</div>

<style>
    .container {
        display: block;
        position: relative;
        background: white;
        aspect-ratio: 1 / 1;
        width: var(--size);
        margin: 0;
        border-radius: 50%;
        z-index: 1;
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
    }
</style>
