<!-- This is a Card component -->
<script lang="ts">
  export let className = '';
</script>

<div class="bg-gray-800 rounded-xl overflow-hidden border border-gray-700 hover:border-purple-500 transition-colors {className}">
  <slot />
</div>
