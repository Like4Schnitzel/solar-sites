<script lang="ts">
    import SolarSystem from "$lib/components/SolarSystem.svelte";
    import Planet from "$lib/components/Planet.svelte";
    import Orbit from "$lib/components/Orbit.svelte";
</script>

<div class="main">
    <h1>It's like a window or something idk</h1>
    <div class="system-container">
        <SolarSystem twinkleSpeed={1}>
            <Orbit width="60%" height="60%" objectSize="30%">
                <Planet fallbackImage="fallback_rainbow.png" fbImgAlt="A rainbow gradient from left to right" url="/example" size=100% />
            </Orbit>
            <!--
            <Orbit width="45%" height="40%" objectSize="100%" rotationTime="4s">
                <Planet fallbackImage="fallback_tf.png" fbImgAlt="The original trollface image" size=20% url="" rotationSpeed={2} />
            </Orbit>
            <Planet fallbackImage="fallback_tf.png" fbImgAlt="The original trollface image" size=20% url="" rotationSpeed={0.5} />
            -->
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
        height: 75%;
        width: 75%;
    }

    .main {
        position: absolute;
        top: 0;
        left: 0;
        height: 100%;
        width: 100%;
        background-color: aliceblue;
    }
</style>
