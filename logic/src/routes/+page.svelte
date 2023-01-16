<script>
  let user = {loggedIn: false};

  const toggle = () => {
    user.loggedIn = !user.loggedIn;
  }
</script>

<div>User login status : {user.loggedIn}</div>

{#if !user.loggedIn}
    <button on:click={toggle}>Log In</button>
{:else}
    <button on:click={toggle}>Log Out</button>
{/if}
