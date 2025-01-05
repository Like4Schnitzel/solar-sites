<script lang="ts">
    export let size: string;
    export let gradient: string = "radial-gradient(hsl(0, 0%, 100%), hsl(49, 100%, 72%))";
    export let boxShadow: string = "0 0 1em 1em hsl(49, 100%, 72%)";
</script>

<div class="container" style="--size: {size}; --gradient: {gradient}; --box-shadow: {boxShadow}">
    <div class="blur">
        <div class="solid">

        </div>
    </div>
</div>

<style>
    .container {
        display: block;
        position: absolute;
        left: 0;
        right: 0;
        margin-left: auto;
        margin-right: auto;
        aspect-ratio: 1 / 1;
        width: var(--size);
    }
    
    .blur {
        display: block;
        position: relative;
        width: calc(100% - 2px);
        height: calc(100% - 2px);
        box-shadow: var(--box-shadow);
        border-radius: 50%;
        background-color: lime; /* for testing to see if there's a gap between solid and blur (VERY NECESSARY FOR DEBUGGING) */
    }

    .solid {
        display: block;
        position: relative;
        left: -1px;
        top: -1px;
        width: calc(100% + 2px);
        height: calc(100% + 2px);
        background: var(--gradient);
        border-radius: 50%;
    }
</style>
