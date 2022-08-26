<script>
  import Router from "svelte-spa-router";
  import NomeCompleto from "./views/NomeCompleto.svelte";
  import Home from './views/Home.svelte';
  import Repete from "./views/Repete.svelte";
import Buscador from "./views/Buscador.svelte";

  const routes = {
      '/': Home,
      '/nomecompleto': NomeCompleto,
      '/repete': Repete,
      '/buscador': Buscador,
      // '*': NotFound
  }
</script>
<Router {routes}/>
