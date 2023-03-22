<script lang="ts">
  
  import Categoria from "$lib/components/paginas/index/Categoria.svelte";

  import categorias from "$lib/json/categorias.json";

  import { beforeNavigate } from "$app/navigation";
  import { minhaLista } from "$lib/stores/minhaLista";
  import Titulo from "$lib/components/compartilhados/Titulo.svelte";
  import Taglink from "$lib/components/compartilhados/Taglink.svelte";

  $: listaVazia = $minhaLista.length === 0;

  beforeNavigate((navigation) => {
    if (listaVazia) {
      navigation.cancel();
    }
  });
</script>

<svelte:head>
  <title>Alura Cook</title>
</svelte:head>

<main>
  <div class="buscar-receitas">
    <Taglink href="/receitas">Buscar Receitas!</Taglink>
  </div>

  <Titulo tag="h1">Ingredientes</Titulo>
  <div class="info">
    <p>Selecione abaixo os ingredientes que voce deseja usar nesta refeicao:</p>
  </div>
  <ul class="categorias">
    {#each categorias as categoria (categoria.nome)}
      <li>
        <Categoria {categoria} />
      </li>
    {/each}
  </ul>
</main>

<style>
  .info {
    margin-bottom: 3.375rem;
  }

  .info > p {
    line-height: 2rem;
  }

  .categorias {
    margin-bottom: 4.6875rem;

    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 1.5rem;
  }

  .buscar-receitas {
    display: flex;
    justify-content: center;
    margin-top: 1.5rem;
    margin-bottom: 1.5rem;
  }
</style>
