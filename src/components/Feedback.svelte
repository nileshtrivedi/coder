```svelte
<script>
  import { writable } from 'svelte/store';

  // Create a writable store for feedback
  export const feedback = writable('');

  // Function to update feedback
  export function updateFeedback(newFeedback) {
    feedback.set(newFeedback);
  }
</script>

<div id="feedback" class="p-4 bg-green-200 rounded-md mt-4">
  <h2 class="text-lg font-bold">Feedback</h2>
  <p class="mt-2 text-sm">{$feedback}</p>
</div>
```