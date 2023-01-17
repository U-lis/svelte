<script>
  import {createEventDispatcher} from "svelte";
  import Inner from "./Inner.svelte";

  const dispatch = createEventDispatcher();

  const forward = (e) => {
    dispatch("message", e.detail);
  }
</script>

<Inner on:message={forward}/>
