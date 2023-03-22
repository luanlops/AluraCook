<script lang="ts">
    import Tag from "$lib/components/compartilhados/Tag.svelte";
  import { minhaLista } from "$lib/stores/minhaLista";
    import MeuIngrediente from "./MeuIngrediente.svelte";
    
  
</script>

<section class="minha-lista">
  <ul class="meus-ingredientes">
    {#each $minhaLista as ingrediente (ingrediente)}
      <li>
        <MeuIngrediente {ingrediente}></MeuIngrediente>
      </li>
    {/each}
  </ul>
</section>

<style>
  .minha-lista {
    padding-bottom: 1.625rem;
  }

  .meus-ingredientes {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 0.75rem 1.875rem;
  }
</style>
