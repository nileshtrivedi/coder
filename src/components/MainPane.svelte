```svelte
<script>
  import { onMount } from 'svelte';
  import { writable } from 'svelte/store';
  import Topic from './Topic.svelte';
  import Question from './Question.svelte';
  import Feedback from './Feedback.svelte';

  let selectedTopic = writable(null);
  let topics = []; // This will be fetched or hardcoded in real scenario

  onMount(async () => {
    // Fetch topics or hardcode them here
  });

  const selectTopic = (topicId) => {
    selectedTopic.set(topics.find(topic => topic.id === topicId));
  };

  $: if ($selectedTopic) {
    import(`../assets/images/${$selectedTopic.image}`);
    import(`../assets/videos/${$selectedTopic.video}`);
  }
</script>

<div id="mainPane" class="main-pane">
  {#if $selectedTopic}
    <Topic {selectedTopic} />
    {#each $selectedTopic.questions as question (question.id)}
      <Question {question} />
      <Feedback {question} />
    {/each}
  {:else}
    <p>Select a topic from the sidebar to start learning!</p>
  {/if}
</div>

<style>
  @import '../styles/mainPane.css';
</style>
```