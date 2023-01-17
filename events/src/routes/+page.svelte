<script>
  let m = {x: 0, y: 0};

  const handleMouseMove = (e) => {
    m.x = e.clientX;
    m.y = e.clientY;
  }
</script>

<div on:mousemove={handleMouseMove}>The mouse position is: {m.x}, {m.y}</div>

<style>
  div {
      width: 100%;
      height: 50%;
  }
</style>
