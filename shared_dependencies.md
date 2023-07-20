1. **Exported Variables**
   - `topics` from `src/data/topics.js`: This is the data schema for the catalog of topics. It is used in `src/components/Sidebar.svelte` to display the list of topics and in `src/components/MainPane.svelte` to display the selected topic's content.

2. **Data Schemas**
   - `Topic` in `src/data/topics.js`: This schema defines the structure of a topic, including its title, content (text, images, videos), and questions.

3. **DOM Element IDs**
   - `sidebar` in `src/components/Sidebar.svelte`: This is the container for the list of topics.
   - `mainPane` in `src/components/MainPane.svelte`: This is the container for the selected topic's content.
   - `topic` in `src/components/Topic.svelte`: This is the container for a single topic in the sidebar.
   - `question` in `src/components/Question.svelte`: This is the container for a question within a topic.
   - `feedback` in `src/components/Feedback.svelte`: This is the container for the feedback after a user submits an answer.

4. **Message Names**
   - `topicSelected` in `src/components/Sidebar.svelte`: This message is dispatched when a user selects a topic from the sidebar. It is listened for in `src/components/MainPane.svelte` to update the displayed content.

5. **Function Names**
   - `selectTopic` in `src/components/Sidebar.svelte`: This function is triggered when a user selects a topic. It dispatches the `topicSelected` message.
   - `submitAnswer` in `src/components/Question.svelte`: This function is triggered when a user submits an answer to a question. It updates the `feedback` component with the result.
   - `updateFeedback` in `src/components/Feedback.svelte`: This function is triggered when the `submitAnswer` function is called. It updates the feedback displayed to the user.