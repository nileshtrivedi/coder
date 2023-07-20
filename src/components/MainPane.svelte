```svelte
<script>
  import { onMount } from 'svelte';
  import Topic from './Topic.svelte';
  import Question from './Question.svelte';
  import Feedback from './Feedback.svelte';
  import { topics } from '../data/topics.js';

  let selectedTopic = null;

  onMount(() => {
    window.addEventListener('topicSelected', (event) => {
      selectedTopic = topics.find(topic => topic.title === event.detail);
    });
  });
</script>

<div id="mainPane" class="flex flex-col p-4">
  {#if selectedTopic}
    <Topic {selectedTopic} />
    <div class="mt-4">
      {#each selectedTopic.questions as question}
        <Question {question} />
      {/each}
    </div>
    <Feedback />
  {:else}
    <div class="text-center text-gray-500">Select a topic to start learning</div>
  {/if}
</div>

<style>
  #mainPane {
    width: calc(100% - 250px);
  }
</style>
```