# Weekend Challenge 11 - React-Redux Feedback Form

## Instructions

Reviewing code is an important role developers play. We're going to practice reviewing code from others.

- Get the repo url from your partner
- Get your partner's project running on your computer
- Review the code from your partner and give relevant feedback
- Complete the Markdown section and submit that in the notes section on the assignment app. (Make sure you include who's code you reviewed.)

Practicing compassionate code reviews is important (you can learn more from this video on the topic: https://www.youtube.com/watch?v=Ea8EiIPZvh0 )

## Review Checklist

## Base Required Features 

- Multi-Part Form:  
  - [ no ] Able to add feedback
    - [ no ] Data collected on individual pages & components
    - [ yes ] Click on next takes you to the next page in sequence
    - [ no ] Data saves in DB after *all* the parts are completed (not piecemeal)
    - [ yes ] Thank you page takes you back to the first view
    - [ no ] Old Data is cleared on form completion

- Client code:
  - [ yes ]  Individual components for each form part
  - [ yes ]  Redux setup complete
    - [ yes ] Store linked to react with `<Provider>`
    - [ yes ] Store setup with reducer(s) and logger middleware 
  - [ ] Reducers & Actions Working
    - [ yes ] Actions are in SCREAMING_SNAKE_CASE and semantically named
    - [ yes ] Actions have a `type` key, and `payload` if sending data
    - [ no ] Reducers are returning a new state, or the old state (not mutating)
    - [ yes ] Reducers are using spread correctly (to keep old data, while adding new)
  - [ yes ] Review Component shows at all times with current redux state
  - [ yes ] React-Redux Working
    - [ yes ] Dispatching actions onClick
    - [ yes ] Grabbing data from the redux store with `useSelector`
  - [ yes ] Axios POST request to add feedback


- Server code:   
  - [ yes ] Router made for GET, POST


## General Items
Feedback should be provided for these items, but they do not impact scoring.

- Git 
  - [ yes ] Multiple git commits showing incremental progress
  - [ yes ] Commits are descriptive of the changes made or feature added 
  - [ yes ] Has .gitignore with node_modules
  - [ no ] Readme file updated (assuming this is previously discussed)
- Code Style 
  - [ no ] Appropriate amount of code comments
  - [ yes ] Code is consistently formatted
- Client
  - [ yes ] Appropriate use of HTML tags
  - [ yes ] Basic CSS styling with margins/padding


## Stretch Goals
First must be complete for score of  _Exceeds Expectations_

- Previous Steps
  - [ ] allows a user to go to a previous step, either directly or by cycling backward thru the steps
  - [ ] user can update their score for a step
    - [ ] new score is validated to not be empty
    - [ ] redux is updated with new score
  - [ ] user can continue on to review page and submit as in Base Mode


- Admin View
  - [ ] All entries are visible with correct data from inputs
    - [ ] Most recent is at the top
  - [ ] Can Delete an entry
    - [ ] User is prompted before deleting
  - [ ] Axios GET request to get all feedback for `/admin` view in componentDidMount

  Busywork Goals, consider removing or making more useful

- [ ] Styling with Material UI
- [ ] Ability to flag a feedback item on `/admin` for further review
- [ ] Deployed to Heroku


## Markdown

```
Hey Kay,

General Feedback.

---
| Functional Requirements | Complete? no |
| --- | :---: |
| Multi page form with client side routing and navigation (next button) | yes |
| Data stored in Redux when navigating from page to page | no |
| User is notified when trying to leave a blank score | no |
| Review Component displays scores and comments from current redux state | no |
| Submit button sends data to the server via Axios | yes |
| Confirmation Page displays after data is POSTed to the server | yes |
| Button on Confirmation Page clears Redux and starts a new survey | no |
| Views are broken down into components | yes |

---
### Notes:

Notes on the above Functional Requirements.

---
| General Items | Complete? |
| --- | :---: |
| More than 15 git commits | yes |
| Commits are descriptive of the changes made or feature added | yes |
| Readme file updated | no |
| Appropriate amount of code comments | no |
| Code is consistently formatted | yes |
| Server code organized with router & module files | yes |

---
### Notes:

Notes on General Items

Kay,

You had a great amount of commits and you really had all the right pieces of code! My main feedback is that some of your code is just located in the wrong place. Unfortunately, nothing was failing by erroring, but as you noticed your page was submitting just upon touching the form. This can be resolved by examining what function you are calling in the form element. In your case, you were calling the function upon CLICKING the form, not SUBMITTING the form. This can be resolved by simply modifying your onClick in the <form> element to be onSubmit - or - you can move your onClick to the <Button> element.

Additionally, as you are watching the redux logger, it tells you if you are receiving the correct data. When you were clicking on the next button, your data was not being properly dispatched. Upon further examination I noticed that you do, in fact, have a function that is trying to target the event.target.value, but it is located in your input LABEL, not the input itself. Another instance of the right code in the wrong place. Once I moved these two pieces around your app worked really well and posted to the database!

The last thing, quick thing, I noticed was you do have an action.type equivalent to 'EMPTY' but there is no where that is listening for that specific action.type - so your data is not being reset at the end of the submission.

Overall, really good work! Just a few minor adjustments and your code is super successful!

```
