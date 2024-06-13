<script lang="ts">
    export let width: string;
    export let height: string;
    export let rotationTime = "10s";
    export let objectSize: string;
</script>

<div class="viewport" style="--width: {width}; --height: {height}; --rotation-time: {rotationTime}; --object-size: {objectSize};">
    <div class="horizontal-line">
        <div class="the-spinner">
            <div class="the-object">
                <slot />
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
    }

    .horizontal-line {
        position: inherit;
        height: 100%;
        aspect-ratio: 1 / 1;
        top: 50%;
        left: 0;
        animation: mX var(--rotation-time) ease 0s infinite;
    }

    .the-spinner {
        position: absolute;
        width: 100%;
        height: 100%;
        top: -50%;
        animation: mO var(--rotation-time) linear 0s infinite;
    }

    .the-object {
        position: absolute;
        top: 0px;
        left: calc(0 - var(--object-size) / 2);
        width: var(--object-size);
        aspect-ratio: 1 / 1;
        animation: mOneg var(--rotation-time) linear 0s infinite;
    }

    @keyframes mX {
        0% { transform: translateX(0);   }
        50% { transform: translateX(var(--width)); }
        100% { transform: translateX(0);   }
    }

    @keyframes mO {
        0% { transform: rotate(0deg);   }
        100% { transform: rotate(360deg); }
    }

    @keyframes mOneg {
        0% { transform: rotate(360deg); }
        100% { transform: rotate(0deg); }
    }
</style>
