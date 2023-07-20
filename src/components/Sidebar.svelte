```svelte
<script>
  import { writable } from 'svelte/store';
  import { onMount } from 'svelte';

  // Shared variable
  export let selectedTopic = writable(null);

  // Mock data for topics
  let topics = [
    { id: 1, name: 'Addition' },
    { id: 2, name: 'Subtraction' },
    { id: 3, name: 'Multiplication' },
    { id: 4, name: 'Division' },
    // Add more topics as needed
  ];

  // Function to select a topic
  function selectTopic(topicId) {
    selectedTopic.set(topics.find(topic => topic.id === topicId));
  }

  onMount(() => {
    // Select the first topic by default
    selectTopic(topics[0].id);
  });
</script>

<div id="sidebar" class="sidebar">
  <ul class="topic-list">
    {#each topics as topic (topic.id)}
      <li>
        <button on:click={() => selectTopic(topic.id)} class="topic-button">
          {topic.name}
        </button>
      </li>
    {/each}
  </ul>
</div>

<style>
  @import '../styles/sidebar.css';
</style>
```