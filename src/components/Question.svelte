```svelte
<script>
  import { createEventDispatcher } from 'svelte';
  const dispatch = createEventDispatcher();

  let answer = '';

  function submitAnswer() {
    dispatch('answerSubmitted', { answer });
    answer = '';
  }
</script>

<div id="question" class="p-4 bg-white rounded shadow">
  <h2 class="text-xl font-bold mb-2">{question.title}</h2>
  <p class="text-gray-700 mb-4">{question.text}</p>
  <input type="text" bind:value={answer} class="border p-2 rounded w-full mb-2" placeholder="Your answer here..." />
  <button on:click={submitAnswer} class="bg-blue-500 text-white px-4 py-2 rounded shadow">Submit</button>
</div>
```