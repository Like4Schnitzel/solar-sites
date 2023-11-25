<script lang="ts">
    import TwinklingStars from "./TwinklingStars.svelte";

    export let twinkleSpeed = 1;
</script>

<div class="solar-system">
    <div class="planet">
        <slot />
    </div>
    <div class="twinkling-stars">
        <TwinklingStars twinkleSpeed={twinkleSpeed} />
    </div>
</div>

<style>
    .solar-system {
        height: 100%;
        background-color: black;
    }

    .twinkling-stars {
        display: none;
    }
</style>