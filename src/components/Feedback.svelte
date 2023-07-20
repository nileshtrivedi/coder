```svelte
<script>
  import { onMount } from 'svelte';
  import { userAnswer } from '../store.js';

  let feedback = '';

  const getFeedback = () => {
    if (userAnswer === correctAnswer) {
      feedback = 'Correct! Great job!';
    } else {
      feedback = 'Incorrect. Try again!';
    }
  };

  onMount(() => {
    getFeedback();
  });
</script>

<style>
  @import '../styles/feedback.css';
</style>

<div id="feedback" class="feedback-container">
  <p>{feedback}</p>
</div>
```