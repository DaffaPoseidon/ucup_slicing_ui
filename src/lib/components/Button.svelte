<!-- This is a Button component -->
<script lang="ts">
  export let variant: 'primary' | 'secondary' = 'primary';
  export let href: string | undefined = undefined;
  export let className = '';
  
  const baseStyles = "rounded-lg transition-colors";
  
  $: buttonClasses = variant === 'primary' 
    ? `${baseStyles} bg-purple-600 hover:bg-purple-700 text-white ${className}`
    : `${baseStyles} border border-white text-white hover:bg-white hover:text-purple-600 ${className}`;
</script>

{#if href}
  <a {href} class={buttonClasses}>
    <slot />
  </a>
{:else}
  <button class={buttonClasses} on:click>
    <slot />
  </button>
{/if}
