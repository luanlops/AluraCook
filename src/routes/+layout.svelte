<script>
  import "../app.css";
  import { minhaLista } from "$lib/stores/minhaLista";
  import MinhaLista from "$lib/components/paginas/layout/MinhaLista.svelte";
  import Cabecalho from "$lib/components/paginas/layout/Cabecalho.svelte";
  import Rodape from "$lib/components/paginas/layout/Rodape.svelte";
</script>

<div class="container-principal">
  <Cabecalho />
  <div class="estilo-principal">
    <div>
      <h2 class="minha-lista">Sua Lista:</h2>
      {#if $minhaLista.length}
        <MinhaLista />
      {/if}
    </div>
    <div class="divisoria" />
    <slot />
  </div>
  <Rodape />
</div>

<style>
  .divisoria {
    width: 40vw;
    height: 2px;
    background-color: var(--verde);
    margin: 0 auto;
    margin-bottom: 1.5rem;
  }
  .container-principal {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
  }

  .estilo-principal {
    text-align: center;
    padding: 0 5vw 3.375rem;
    flex: 1;
  }
  .minha-lista {
    font-size: 1.5rem;
    color: var(--laranja);
    margin-bottom: 1.5rem;
    line-height: 2rem;
    font-weight: 700;
  }
</style>
