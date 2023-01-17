<script>
  import Inner from "../components/Inner.svelte";

  let m = {x: 0, y: 0};
  let mm = {x: 0, y: 0};

  const handleMouseMove = (e) => {
    m.x = e.clientX;
    m.y = e.clientY;
  }

  const handleAlert = () => {
    alert("You can see me just one time");
  }

  const handleMessage = (e) => {
    // data from Inner.svelte: {text: "hello"} in e.detail
    alert(e.detail.text);
  };
</script>

<div on:mousemove={handleMouseMove}>The mouse position is: {m.x}, {m.y}</div>
<div on:mousemove={e=> mm = {x: e.clientX, y: e.clientY}}>The mouse position is: {mm.x}, {mm.y}</div>
<button on:click|once={handleAlert}>One time alert</button>

<!-- dispatch message event from Inner.svelte -->
<Inner on:message={handleMessage}></Inner>

<style>
  div {
      width: 100%;
      height: 20%;
  }
</style>
