<script>
  let cep = "";
  const dados = {
      bairro: "",
      cep: "",
      ddd: "",
      localidade: "",
      logradouro: "",
      uf: ""
    }
  const pesquisa = (event) => {
  fetch(`https://viacep.com.br/ws/${cep}/json/`).then((response) => {
    return response.json()
  }).then((jsonBody) => {
      dados.bairro = jsonBody.bairro
      dados.cep = jsonBody.cep
      dados.localidade = jsonBody.localidade
      dados.ddd = jsonBody.ddd
      dados.logradouro = jsonBody.logradouro
      dados.uf = jsonBody.uf
  })
}
</script>

<form>
  <input class="cep" type="text" placeholder="CEP" bind:value={cep}>
  <button on:click={pesquisa}>
    Pesquisar
  </button>
  <div class="resultado busca-cep">
    <ul>
      <li><strong>CEP:</strong> {dados.cep}</li>
      <li><strong>Estado:</strong> {dados.uf}</li>
      <li><strong>Cidade:</strong> {dados.localidade}</li>
      <li><strong>Bairro:</strong> {dados.bairro}</li>
      <li><strong>Rua:</strong> {dados.logradouro}</li>
      <li><strong>DDD:</strong> {dados.ddd}</li>
    </ul>
  </div>
</form>

<style>
  form input {
    color: #fff;
  }
  .resultado {
    font-size: 24px;
  }
</style>