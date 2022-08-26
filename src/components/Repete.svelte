<script>
  let elemento = "";
  let numero;

  const repeteElementos = (event) => {
    event.preventDefault()
    document.querySelector(".resultado").innerHTML =  elemento.repeat(numero).split("").join(" ")
  }
</script>

<form>
<input type="text" placeholder="Elemento" bind:value={elemento}>
<input type="number" placeholder="Quantidade" bind:value={numero}>
<button on:click={repeteElementos}>Repetir</button>
<div class="resultado"></div>
</form>
<style>
  * {
    color: #fff;
  }
</style>