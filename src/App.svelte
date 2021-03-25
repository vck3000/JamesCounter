<script>
  let num = localStorage.getItem("number");

  if (num === null) {
    num = 0;
  } else {
    num = parseInt(num);
  }

  function increment() {
    num += 1;
    save();
  }

  function decrement() {
    num -= 1;
    save();
  }

  function save() {
    localStorage.setItem("number", num);
  }

  document.addEventListener("keydown", (e) => {
    console.log(e.code);
    if (e.code === "KeyJ") {
      decrement();
    } else if (e.code === "KeyK") {
      increment();
    }
  });
</script>

<style>
  * {
    height: 32vh;
    width: 100%;

    font-family: sans-serif;
  }

  p {
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 10rem;
    margin: 0;
  }

  button {
    font-size: 10rem;
    margin: 0;
  }
</style>

<main>
  <button on:click={increment}>+</button>
  <p>{num}</p>
  <button on:click={decrement}>-</button>
</main>

