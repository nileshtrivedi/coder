```svelte
<script>
  import { createEventDispatcher } from 'svelte';
  const dispatch = createEventDispatcher();

  export let topic = {};

  function selectTopic() {
    dispatch('topicSelected', topic);
  }
</script>

<div id="topic" class="p-4 border-b border-gray-200 cursor-pointer hover:bg-gray-100" on:click={selectTopic}>
  <h2 class="text-xl font-bold">{topic.title}</h2>
  <p class="text-sm text-gray-500">{topic.description}</p>
</div>

<style>
  #topic:hover {
    background-color: #f8f8f8;
  }
</style>
```