<script lang="ts">
    import SolarSystem from "$lib/components/SolarSystem.svelte";
    import Planet from "$lib/components/Planet.svelte";
</script>

<body class="main">
    <div>
        <SolarSystem twinkleSpeed={1}>
            <Planet fallbackImage="fallback_rainbow.png" fbImgAlt="A rainbow gradient from left to right" url="/example" size=20% />
            <Planet fallbackImage="fallback_tf.png" fbImgAlt="The original trollface image" size=20% url="" rotationSpeed={2} />
            <!--Planet fallbackImage="fallback_tf.png" fbImgAlt="The original trollface image" size=20% url="" rotationSpeed={0.5} /-->
        </SolarSystem>
    </div>
</body>

<style>
    div {
        border-radius: 5%;
        border: solid lightskyblue 5px;
        margin: auto;
        height: 50%;
        width: 50%;
    }

    .main {
        height: 100%;
        background-color: aliceblue;
    }
</style>
