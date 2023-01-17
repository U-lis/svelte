<script>
  import {createEventDispatcher} from "svelte";

  const dispatch = createEventDispatcher();

  // button click calls this function
  const sayHello = () => {
    // dispatch message event > trigger on:message event
    // See +page.svelte to find on:message
    dispatch("message", {text: "hello"});
  };
</script>

<button on:click={sayHello}>Click to dispatch event</button>
