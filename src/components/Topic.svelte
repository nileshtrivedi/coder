```svelte
<script>
  import { onMount } from 'svelte';
  import Question from './Question.svelte';
  import { selectedTopic, topicContent } from '../store.js';

  let topic = {};

  onMount(async () => {
    $selectedTopic.subscribe(value => {
      topic = $topicContent.find(t => t.id === value);
    });
  });
</script>

<style>
  @import '../styles/topic.css';
</style>

<div id="topic" class="topic-container">
  <h2 class="topic-title">{topic.name}</h2>
  <img class="topic-image" src="{topic.image}" alt="{topic.name}" />
  <p class="topic-content">{topic.content}</p>
  <video class="topic-video" controls>
    <source src="{topic.video}" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  <div class="questions-container">
    {#each topic.questions as question (question.id)}
      <Question {question} />
    {/each}
  </div>
</div>
```