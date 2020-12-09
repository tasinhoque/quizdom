## Quiz Play Subsystem

### Categorization of quizzes:

1. Based on subscription:
   1. Subscribed
   2. Unsubscribed
2. Based on type:
   1. Quiz
   2. Survey
3. Based on field
   1. Health
   2. Job
   3. Politics/Election

### Pages:

1. `Player Home`: This page will contain `Quiz Card`s. There will be multiple
   filters for the categories. For example, a player can filter all quizzes which
   are related to health. There will be sponsored quizzes which the player can't
   just filter out.
2. `Quiz Home`: This page will display all the details of a quiz that we couldn't
   show in the `Quiz Card` component (in addition to existing infos), which
   includes:
   1. Description: Some details about the quiz.
   2. Feedbacks: We've to implement this section as implemented in Google Play
      Store.
   3. Leave feedback: Only available if a player attempted the quiz.
   4. Leader board: Only available if a player attempted the quiz.
   5. Statistics: If it's a survey, we can show a pie chart for each survey
      question. Otherwise, we can show the average marks for the quiz.
3. `Quiz Play`: This page will contain multiple stages. There will be a bunch of
   `Question Card`s in each stage.

### Components:

1. `Quiz Card`: This card will have the following UI elements:
   1. Title
   2. Cover Image
   3. Creator
   4. Publication Date
   5. Total players who participated
   6. Average Rating
   7. Subscribe/unsubscribe button
   8. Type tag
   9. Field tag
