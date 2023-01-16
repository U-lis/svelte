<script>
  let count = 0;
  $: doubled = count * 2;

  const handleIncrement = () => {
    count += 1;
  };

  const resetCount = () => {
    count = 0;
  };

  $: {
    console.log(count);
    if (count > 9) {
      console.log("It's to high");
      count = 9;
    }
  }
</script>

<div> Click count: {count} {count <= 1 ? "time" : "times"} </div>
<div> Doubled click count: {doubled} {doubled < 2 ? "time" : "times"} </div>
<button on:click={handleIncrement}>Click!</button>
<button on:click={resetCount}>Reset</button>
