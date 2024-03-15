<script lang="ts">
    export let twinkleSpeed = 1;
</script>

<div class="the-void">
    <div class="solar-system" style="--twinkle-speed: {70/twinkleSpeed}s">
        <slot />
    </div>
</div>

<style>
    @keyframes background-scroll {
        0% {
            background-position: 0 0, 0 0;
        }
        100% {
            background-position: 0 0, 1000px 0;
        }
    }
    
    .solar-system {
        background: url("stars.png") 0, url("twinkling.png") 0;
        width: 100%;
        height: 100%;
        animation: background-scroll var(--twinkle-speed) infinite linear;
    }

    .the-void {
        background-color: black;
    }
</style>
