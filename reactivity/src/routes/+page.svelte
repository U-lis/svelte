<script>
  let count = 0;

  const handleIncrement = () => {
    count += 1;
  };

  const resetCount = () => {
    count = 0;
  };
</script>

<div>
    Click count: {count} {count <= 1 ? "time" : "times"}
</div>
<button on:click={handleIncrement}>Click!</button>
<button on:click={resetCount}>Reset</button>
