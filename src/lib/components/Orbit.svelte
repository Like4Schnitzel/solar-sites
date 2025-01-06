<script lang="ts">
    export let width: string;
    export let height: string;
    export let rotationTime = "10s";
    export let objectSize: string;
</script>

<div class="viewport" style="--width: {width}; --height: {height}; --rotation-time: {rotationTime}; --object-size: {objectSize};">
    <div class="the-pusher"></div>
    <div class="horizontal-line">
        <div class="the-spinner">
            <div class="the-object">
                <slot gradientTurnTime={rotationTime} />
            </div>
        </div>
    </div>
</div>

<style>
    .viewport {
        position: absolute;
        width: var(--width);
        height: var(--height);
        left: 0;
        right: 0;
        margin-left: auto;
        margin-right: auto;
        display: flex;
        pointer-events: none;
    }

    .the-pusher {
        flex-grow: 0;
        animation: expandPusher var(--rotation-time) ease-in-out 0s infinite;
    }

    .horizontal-line {
        position: relative;
        height: 100%;
        aspect-ratio: 1 / 1;
        top: 50%;
        left: 0;
    }

    .the-spinner {
        position: absolute;
        width: 100%;
        height: 100%;
        top: -50%;
        animation: mO var(--rotation-time) linear 0s infinite;
    }

    .the-object {
        rotate: 90deg;
        position: absolute;
        top: 0px;
        left: calc(0 - var(--object-size) / 2);
        width: var(--object-size);
        aspect-ratio: 1 / 1;
        animation: reverse mO var(--rotation-time) linear 0s infinite;
    }

    @keyframes expandPusher {
        0% { flex-grow: 0; }
        50% { flex-grow: 1; }
        100% { flex-grow: 0; }
    }

    @keyframes mO {
        0% { transform: rotate(-45deg);   }
        100% { transform: rotate(315deg); }
    }
</style>
