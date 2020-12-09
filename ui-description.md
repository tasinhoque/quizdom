## Quiz Play and Result Delivery Subsystems

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
   filters for those cards based on the categories. For example, a player can
   filter all quizzes which are related to health. There will be sponsored
   quizzes which the player can't just filter out. At the top of the page, we'll
   see:

   1. Player's avatar and name at the top-right corner
   2. Total quizzes the player participated in at the top-right corner
   3. Logo and name of the platform at the top-left corner
   4. Notification: We need to notify the player when a scheduled (subscribed)
      quiz starts. This is mainly why we'd need a notification section. But
      aside from this, we can show other types of notifications also.

      A bell icon with the number of unread notification will be
      shown at the top-right corner. When the user clicks on it, an
      [overlay](https://www.figma.com/blog/introducing-overlays-taking-prototyping-to-the-next-layer/)
      will come up. There will be a bunch of `Notification Item`s on it.

2. `Quiz Home`: This page will display all the details of a quiz that we couldn't
   show in the `Quiz Card` component (in addition to existing infos), which
   includes:
   1. Description: Some details about the quiz.
   2. Feedbacks: We've to implement this section as implemented in Google Play
      Store.
   3. Leave feedback: Only available if a player attempted the quiz.
   4. Link to `Leader Board`: Only available if a player attempted the quiz.
   5. Statistics: If it's a survey, we can show a pie chart for each survey
      question. Otherwise, we can show the average marks for the quiz.
   6. Duration
   7. Start time (if it's a scheduled quiz)
   8. Link to `My Submission`: Only available if a player attempted the quiz.
3. `Quiz Play`: This page will contain multiple stages. There will be a bunch of
   `Question Card`s in each stage. At the top of the page, we'll show:

   1. Quiz title
   2. Stage title and number (along with total stages)
   3. Cover Image (same as the image used in `Quiz Home`)
   4. Remaining time for the quiz (if it's not survey)
   5. Number of questions completed (along with total questions)

   At the end of `Quiz Play`, the player will be redirected to the `My Submission`
   page (if auto-evaluation is available).

4. `Leader Board`: This paged is linked to the `Quiz Home` page. Basically,
   we'll show a [table](https://material-ui.com/components/tables/) here. The
   table will have the following columns:

   1. Rank
   2. Player (cells of this column will contain both avatar and name)
   3. Total Marks Obtained

   Above the table, we need to show the total marks.

   Note: There will be no `Leader Board` page for surveys.

5. `My Submission`: This page is linked to the `Quiz Home` page. We'll show
   correct answer for each question, along with the player's answer here. This
   page can be similar to the `Quiz Play` page, since there is a possibility of
   reusing the `Question Card` component (though we may need to modify it slightly).

   Note: If we're dealing with a survey, we'll just show the player's response.

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
2. `Question Card`: This card will have the following UI elements:
   1. Question title
   2. Image (optional)
   3. Radio buttons (if MCQ type question)
   4. Checkboxes (optional)
   5. File input button (optional): We can set the type of files the player can
      upload. For example, if the expected format is PDF, if the player tries to
      upload a audio file, the submission will be rejected (we can show a dialog
      box explaining what went wrong).
   6. [Select](https://material-ui.com/components/selects/)s (optional)
   7. [Slider](https://material-ui.com/components/slider/)s (optional)
   8. [Switch](https://material-ui.com/components/switches/)s (optional)
   9. Text Fields (optional): It can be either single line or multi line.
3. `Notification Item`: The items can be of any of the following types:
   1. A scheduled quiz has started (we need keep a button linking to
      `Quiz Play`)
   2. Marks published for a quiz with manual evaluation (there will be a button
      linking to the `My Submission` page).
