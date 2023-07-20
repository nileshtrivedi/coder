```svelte
<script>
  import { createEventDispatcher } from 'svelte';
  import { topics } from '../data/topics.js';
  const dispatch = createEventDispatcher();

  function selectTopic(topic) {
    dispatch('topicSelected', topic);
  }
</script>

<div id="sidebar" class="w-1/4 h-screen overflow-auto border-r border-gray-200 p-4">
  <h2 class="text-xl font-bold mb-4">Topics</h2>
  <ul>
    {#each topics as topic (topic.id)}
      <li>
        <button 
          class="text-left w-full text-gray-700 hover:bg-gray-100 px-2 py-1 rounded"
          on:click={() => selectTopic(topic)}
        >
          {topic.title}
        </button>
      </li>
    {/each}
  </ul>
</div>

<style>
  #sidebar {
    @apply w-1/4 h-screen overflow-auto border-r border-gray-200 p-4;
  }
</style>
```