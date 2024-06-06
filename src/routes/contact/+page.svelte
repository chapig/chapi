<script lang="ts">
    import Header from '$lib/components/header/header.svelte';
    import { onMount } from 'svelte';

    onMount(() => {
        document.title = 'Resume | Luis Chaparro';
    });

    let pdfUrl = '/Luis Chaparro CV EN.pdf';
</script>
<Header />
<iframe src="{pdfUrl}" width="100%" height="800px" title="Resume"></iframe>

<style>
  iframe {
    border: none;
  }
</style>