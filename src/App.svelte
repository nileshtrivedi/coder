```svelte
<script>
  import Sidebar from './components/Sidebar.svelte';
  import MainPane from './components/MainPane.svelte';
  import { topics } from './data/topics.js';
  let selectedTopic = topics[0];
</script>

<main class="flex h-screen bg-gray-100">
  <Sidebar bind:selectedTopic={selectedTopic} class="w-1/4 bg-white shadow" />
  <MainPane {selectedTopic} class="w-3/4 bg-gray-100" />
</main>

<style>
  main {
    overflow: hidden;
  }
</style>
```