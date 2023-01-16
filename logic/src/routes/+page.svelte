<script>
  import Thing from "../components/Thing.svelte";

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

  let cats = [
    {id: 'J---aiyznGQ', name: 'Keyboard Cat'},
    {id: 'z_AbfPXTKms', name: 'Maru'},
    {id: 'OUtn3pvWmpg', name: 'Henri The Existential Cat'}
  ];

  const thingsOriginal = [
    {id: 1, name: 'apple'},
    {id: 2, name: 'banana'},
    {id: 3, name: 'carrot'},
    {id: 4, name: 'doughnut'},
    {id: 5, name: 'egg'},
  ];

  let things = [
    {id: 1, name: 'apple'},
    {id: 2, name: 'banana'},
    {id: 3, name: 'carrot'},
    {id: 4, name: 'doughnut'},
    {id: 5, name: 'egg'},
  ];

  const removeFirst = () => {
    things = things.slice(1);
  };
  const resetThings = () => {
    things = thingsOriginal;
  };
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

<hr>

<ul>
    {#each cats as cat, i}
        <li>No.{i + 1}: {cat.name}</li>
    {/each}
</ul>

<hr>

{#each things as thing}
    <Thing name={thing.name}></Thing>
{/each}
<button on:click={removeFirst}>Remove First</button>
<button on:click={resetThings}>Reset List</button>
