<script lang="ts">
    import SolarSystem from "$lib/components/SolarSystem.svelte";
    import Orbit from "$lib/components/Orbit.svelte";
    import Planet from "$lib/components/Planet.svelte";
    import Sun from "$lib/components/Sun.svelte";
</script>

<div class="main">
    <h1>It's like a window or something idk</h1>
    <div class="system-container">
        <SolarSystem twinkleSpeed={1}>
            <Sun size=10% />
            <Orbit width=60% height=70% objectSize=30% rotationTime=20s>
                <Planet fallbackImage="fallback_rainbow.png" fbImgAlt="A rainbow gradient from left to right" url="/example" size=100% gradientTurnTime=20s />
            </Orbit>
            <Orbit width=20% height=30% objectSize=20% rotationTime=4s>
                <Planet fallbackImage="fallback_tf.png" fbImgAlt="The original trollface image" size=100% url="" rotationSpeed={2} gradientTurnTime=4s />
            </Orbit>
        </SolarSystem>
    </div>
</div>

<style>
    h1 {
        font-family:'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
        width: 100%;
        text-align: center;
    }

    .system-container {
        border-radius: 10%;
        border: solid lightskyblue 5px;
        overflow: hidden;
        margin: auto;
        height: 90%;
        width: 95%;
    }

    .main {
        position: absolute;
        top: 0;
        left: 0;
        height: 100%;
        width: 100%;
        background-color: darkgray;
        overflow: hidden;
    }
</style>
