<script lang="ts">
    import TwinklingStars from "./TwinklingStars.svelte";

    export let twinkleSpeed = 1;
</script>

<body class="main">
    <TwinklingStars twinkleSpeed={twinkleSpeed} />
</body>

<style>
    .main {
        height: 100%;
        background-color: black;
    }
</style>