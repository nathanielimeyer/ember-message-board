# ember-message-board

## Description

This application is a question and answer message board. The home page will display a list of questions and their authors. Clicking any question will bring up the question along with additional notes from the author and corresponding answers.

## Planning

1. Configuration / dependencies

2. Specs

|Requirement|input|output|
|-----------|:---:|:----:|
|From the homepage, a user asks a question | "Name: Bob" "Question: Does Ember solve more problems than it creates?" "Notes: I'm asking because it seems like it's supposed to simplify things but it makes so many other things so much harder."|Question and author name are shown on index|
|From the homepage, a user clicks on a question| *Click* |Question, author name and notes are shown on question details|
|From all pages, users can click navbar links:|Click: Home|User is returned to homepage|
||||
|From the question details page, a user can edit a question|Click: Edit|An update form is presented|
|" "|User fills out update form and saves|The question is updated and the user is returned to question details|
|From the question details page, a user can submit an answer|Click: Answer|An add answer form is presented|
|" "|"Answer: Good question, you can do a lot with Ember if you invest a lot of time. But you could probably get further investing that time in a different framework."; "Name: Dave"|The answer is added and the user is returned to question details|
||||


3. Integration
  * Routes:
    * index:
      * list questions, link to question details
      * add new question form (new-question component)
    * question:
      * show question details
      * uses question-tile for edits
      * uses review-tile
    * About? Contacts? etc?
  * Components:
    * new-question (on index route)
      * submits data, routes to index
    * question-detail:
      * assists question route in displaying question detail
    * question-tile:
      * assists question route in displaying question detail
      * user can edit question
    * new-answer (on question route)
      * submits data, routes to question
    * answer-tile
      * assists question route in displaying answer detail
    * update question
      * called from question-tile, assists in editing a question
  * Models
    * Question
      * author
      * question
      * notes
      * answers (has many)
    * Answer
      * author
      * answer
      * question (belongs to)

4. UX/UI
  * Do some styling so this doesn't look sad and barren

5. Polish
  * Check for refactoring
  * Check readme

## Prerequisites

You will need the following things properly installed on your computer.

* [Git](https://git-scm.com/)
* [Node.js](https://nodejs.org/) (with NPM)
* [Bower](https://bower.io/)
* [Ember CLI](https://ember-cli.com/)
* [PhantomJS](http://phantomjs.org/)

## Installation

* `git clone https://github.com/nathanielimeyer/ember-message-board.git` this repository
* `cd ember-message-board`
* `npm install`
* `bower install`

## Running / Development

* `ember serve`
* Visit your app at [http://localhost:4200](http://localhost:4200).

### Running Tests

* `ember test`
* `ember test --server`

### Building

* `ember build` (development)
* `ember build --environment production` (production)

## Further Reading / Useful Links

* [ember.js](http://emberjs.com/)
* [ember-cli](https://ember-cli.com/)
* Development Browser Extensions
  * [ember inspector for chrome](https://chrome.google.com/webstore/detail/ember-inspector/bmdblncegkenkacieihfhpjfppoconhi)
  * [ember inspector for firefox](https://addons.mozilla.org/en-US/firefox/addon/ember-inspector/)
