<script lang="ts">
	import { onMount } from 'svelte';

	export let heading = '';
	export let description = '';
	export let tags = [''];

	let articleURL = '';

	onMount(() => {
		const currentPath = window.location.pathname;
		articleURL = `https://speaktosteve.github.io/${currentPath.split('/').pop()}`;
	});
</script>

<svelte:head>
	<title>speaktosteve | {heading}</title>
	<meta name="description" content={description} />
	<meta name="keywords" content={tags.join(', ')} />
	<link rel="canonical" href={articleURL} />
	<meta http-equiv="refresh" content="0;URL={articleURL}" />
</svelte:head>
