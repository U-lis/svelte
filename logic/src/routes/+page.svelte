<script>
  let user = {loggedIn: false};

  const toggle = () => {
    user.loggedIn = !user.loggedIn;
  }

  let number = 0;
  const increment = () => {
    number += 1;
  };
  const reset = () => {
    number = 0;
  }
</script>

<div>User login status : {user.loggedIn}</div>

{#if !user.loggedIn}
    <button on:click={toggle}>Log In</button>
{:else}
    <button on:click={toggle}>Log Out</button>
{/if}

<hr>

<div>Number: {number}</div>
<div>
    {#if number >= 10}
        Too big!
    {:else if number >= 5}
        Big enough
    {:else}
        Good
    {/if}
</div>
<button on:click={increment}>Click</button>
<button on:click={reset}>Reset</button>
