```svelte
<script>
  import Sidebar from './components/Sidebar.svelte';
  import MainPane from './components/MainPane.svelte';
  import { onMount } from 'svelte';
  import { writable } from 'svelte/store';

  let selectedTopic = writable(null);

  onMount(() => {
    selectedTopic.set(null);
  });

  const selectTopic = (topicId) => {
    selectedTopic.set(topicId);
  };
</script>

<style>
  @import './styles/main.css';
</style>

<main class="flex">
  <Sidebar {selectTopic} bind:selectedTopic={selectedTopic} />
  <MainPane bind:selectedTopic={selectedTopic} />
</main>
```