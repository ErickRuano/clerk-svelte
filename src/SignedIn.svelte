<script>
  import { clerk } from './clerk'
</script>

{#if $clerk.user === undefined}
  <slot name="loading"/>
{:else if $clerk.user !== null}
  <slot />
{/if}


