<script lang="ts">
	import { page } from '$app/stores';

	console.log('init __layout.svelte');

	const log = (value: any) => {
		console.log(value);
		return '';
	};

	$: console.log({ path });
	$: path = $page.path;
</script>

{#if path.endsWith('MyComp')}
	{log('about to display MyComp from __layout.svelte')}
	<p>Comp1 from __layout.svelte</p>
	<slot />
{:else}
	{log('about to display index.svelte from __layout.svelte')}
	<p>index.svelte from __layout.svelte</p>
	<slot />
{/if}

<a href="/">root</a>
<a href="/MyComp">MyComp</a>
