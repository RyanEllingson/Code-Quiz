# Code-Quiz
Homework 4

URL for the live app is here:
https://ryanellingson.github.io/Code-Quiz/

# Project description

![Screenshot of landing page for code quiz](https://github.com/RyanEllingson/Code-Quiz/blob/8f2243984895927040982d3b435b63922bcc0c38/assets/images/screenshot1.JPG)

This quiz asks the user a series of questions about javascript and times how long it takes to answer them all.  The user is given 75 seconds to start out with, and each wrong answer results in a 15-second penalty.  The user's final score is equal to the number of seconds left on the clock after the final question is answered.

To start the quiz, the user clicks the "Start Quiz" button on the landing page.

![Screenshot of quiz page](https://github.com/RyanEllingson/Code-Quiz/blob/8f2243984895927040982d3b435b63922bcc0c38/assets/images/screenshot2.JPG)

Once the quiz is started, the user is presented with a question, along with 4 possible answers.  Upon clicking one of the possible answers, the app will tell the user whether their answer was correct or not, deduct 15 seconds from the remaining time if incorrect, then load the next question.

![Screenshot of final page](https://github.com/RyanEllingson/Code-Quiz/blob/8f2243984895927040982d3b435b63922bcc0c38/assets/images/screenshot3.JPG)

Once the final question is answered, the user's final score is shown, and a prompt is given for the user to enter their initials.  When the "Submit" button is clicked, the initials and score are saved to local storage, so even after the browser is refreshed the score will be saved.  The list of saved scores can be seen by clicking the "View High Scores" button.

An interesting challenge in creating this app was creating the html for the quiz questions dynamically using javascript, rather than creating them in the html document and modifying them in javascript.  This was also done for generating the list of high scores.  This provided good practice in navigating the DOM in javascript, along with the use of "this" when creating a button and defining its on-click behavior to check its own text and compare to the correct answer.  Additionally, this app uses a recursive function to generate the quiz questions - the "generateQuestion" creates the buttons for the current question, and defines the on-click behavior of those buttons, which include changing the current question and executing "generateQuestion" again.

A particularly vexing problem was storing an array of objects in local storage and then retrieving them.  I was perplexed to get an error when I tried to add elements to this array saying "myArray.push is not a function."  After doing some research I found that for arrays to behave properly you need to convert them to a string when you save them to local storage, then convert them from a string back to an array when you retrieve them again.

