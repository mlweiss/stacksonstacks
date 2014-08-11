# Stacks on Stacks

## Takeaways
---

###General
Don't commit unused code.  


###Seeding
 - Seperate your data from seeding logic. 
 	- ruby file that imports YML/JSON/Ruby Hash literals
 

###Testing

Feature: Use `data-` tags for identifying elements that will later be grabbed by jQuery and Capybara tests. 

 - this allows changed to be made to html and css without breaking anything else. 
 - For Capybara: find elements with css selectors, not `click 'sign_up'`
 
 

Controllers: Should test side effects on the DB. One should not test that an instance variable was set.

 - Feature tests cover whether variables were passed
 - You did this, good job.
 
 
###Models

 - `has_many` not necessary unless you're using the methods it creates in the code
 	- In your user model, `has_many` questions give you a method `#questions` on `User`. This isn't needed.
 
 - `dependent: :destroy` is a thing, keep it in mind with `has_many` associations. If I delete a question, should its comments/answers also be deleted. The decision is yours but be aware of this option.
 
###Controllers

 - Do not use instance variables when you redirect in a contoller action
 
###Views

 - Don't reference collections in the views, ex: `User.find; Comment.find`
 
###Styling
 - Beware of overspecification. It creates brittle code. `div.questions` should be `.questions`
 - Smaller, modular CSS 
