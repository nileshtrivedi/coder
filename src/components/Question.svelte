```svelte
<script>
  import { createEventDispatcher } from 'svelte';
  const dispatch = createEventDispatcher();

  export let question = {};

  let userAnswer = '';

  function submitAnswer() {
    dispatch('answerSubmitted', { questionId: question.id, userAnswer });
    userAnswer = '';
  }
</script>

<div id="question" class="p-4 bg-white rounded shadow">
  <h2 class="text-xl font-bold mb-2">{question.questionText}</h2>
  <input type="text" bind:value={userAnswer} class="border p-2 rounded w-full" placeholder="Your answer here..." />
  <button on:click={submitAnswer} class="mt-2 bg-blue-500 text-white py-2 px-4 rounded">Submit Answer</button>
</div>

<style>
  #question {
    margin-bottom: 2rem;
  }
</style>
```