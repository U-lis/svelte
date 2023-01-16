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

  let numbers = [];
  $: sum = numbers.reduce((t, n) => t + n, 0);
  const addNumber = () => {
    numbers = [...numbers, Math.floor(Math.random() * 10)];
  };
  const resetNumbers = () => {
    numbers = [];
  };

  // Indirect assignment does not work
  let obj;
  const foo = obj.foo;
  foo.bar = "baz";

  // Indirect assignment does not work
  const noop = (thing) => {
    thing.foo.bar = "baz";
    // But this makes work
    thing = thing;
  }
  noop(obj);

</script>

<div> Click count: {count} {count <= 1 ? "time" : "times"} </div>
<div> Doubled click count: {doubled} {doubled < 2 ? "time" : "times"} </div>
<button on:click={handleIncrement}>Click!</button>
<button on:click={resetCount}>Reset</button>
<hr>
<div>Sum of [ {numbers.join(" + ")} ] = {sum}</div>
<button on:click={addNumber}>Add a number</button>
<button on:click={resetNumbers}>Reset</button>
