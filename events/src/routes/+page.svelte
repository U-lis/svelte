<script>
  let m = {x: 0, y: 0};
  let mm = {x: 0, y: 0};

  const handleMouseMove = (e) => {
    m.x = e.clientX;
    m.y = e.clientY;
  }

  const handleAlert = () => {
    alert("You can see me just one time");
  }
</script>

<div on:mousemove={handleMouseMove}>The mouse position is: {m.x}, {m.y}</div>
<div on:mousemove={e=> mm = {x: e.clientX, y: e.clientY}}>The mouse position is: {mm.x}, {mm.y}</div>
<button on:click|once={handleAlert}>One time alert</button>

<style>
  div {
      width: 100%;
      height: 20%;
  }
</style>
