<script>    
    let count = 0;
    let style = 'background-color: aqua;'
</script>

<body class="main">
    <p>
        Some text
    </p>

    <button on:click={() => {count++}}>
        Increment count
    </button>
    <p>
        Count: {count}
    </p>
</body>

<style>
    .main {
        height: 100%;
        background-color: aqua;
    }
</style>
