<script lang="ts">
    import SolarSystem from "$lib/components/SolarSystem.svelte";
    import Planet from "$lib/components/Planet.svelte";
</script>

<SolarSystem twinkleSpeed={1}>
    <Planet fallbackImage="fallback_tf.png" fbImgAlt="The original trollface image" url="/example" size=20% />
</SolarSystem>
