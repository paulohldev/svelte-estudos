<script>
  let nome = "";
  let sobrenome = "";
  let nomeCompleto = "";

  const juntaNome = (event) => {
    event.preventDefault()
    let texto = document.querySelector(".resultado");
    nomeCompleto = `${nome} ${sobrenome}`
    texto.innerHTML = nomeCompleto.split(" ").join("")
  }
</script>

<form>
<input type="text" placeholder="nome" bind:value={nome}>
<input type="text" placeholder="sobrenome" bind:value={sobrenome}>
<button on:click={juntaNome}>
  Concatenar
</button>
<div class="resultado"></div>
</form>
