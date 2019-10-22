# Day 1
* Architecture
  * Architecture is for you too: Problems that we can find when we write mobile applications and how a good architecture can help us
  * Architectural Paradigms (MVX): MVC, MVP, and MVVM, the rules to apply them properly, and how to implement them
  * SOLID Principles: The five SOLID principles, their motivations, and how to apply them
  * Using Design Patterns: A basic intro to design patterns and their value in writing good code
* Clean Architecture
  * Description and Pieces: The pieces that compose Clean Architecture and understand their purpose
  * The Dependency Rule: How to deal with dependencies properly in architecture
  * Hints for Implementation: How to start creating an application that uses this architecture
* First User Story: Show List
  * Extract Minimum Viable Product: Plan the application that we are going to write and how to approach the implementation of its features
  * Implement the Interactor (Business Logic): Create the type that will contain the business logic of the first user story
  * Implement the Presenter: Create a presenter that provides the semantics to view events and uses business logic
  * Implement the View: Write code for the view that the user will interact with
  * Implement the Entity Gateway: The needs of persistence and how to implement them
  * Connect the Pieces and Make it All Work: Write the glue code so all the pieces of the first user story work as expected


  # Intro
Goal is to understand (clean) architecture and how to apply to real code
- Viper, was migrated from backedn architecture, it applies badly on iOS even worst in Android.
- MVC, MVP, MVVM is just separation of concerns not architecture. It only defines how models interact with hte View for example does not dictate how to manage the network --> THIS is the architecture
- **Martin Fowler** --> reference for architecture, recemended for reading on architectures and pattern 

## MVC
Patterns:
- Observer: between model and contrller and view and controller
- Streategy: change the behaviour based on who you are talking with, for example tables changes the behaviour based on the delegte (strategy), not just view for example sorting --> you can have algorithm as an input (strategy)
- composite: talk with one item or with a grpup of items in the same view --> hide a single view or hide a hirarchy of views (same way of doing it just the consumer chose who to talk with.)
-  Android you can't create a view with a constructor because it needs to inject a lot of contentxt, **http://robolectric.org/** can be a solution.

## MVP
Is basically MVC the key difference is that the relationship between the Presenter and The view is inverted between the Controller and the controller.
The View known the presenter but the presenter do not know the view. **the presenter is view and SDK agnostic, it can be used for example both for a web app and monbile app**
The android activity is in the view part, while in MVC it was in the controller.

## MVVM
Origins from "presentation model principle" 
The ViewModel describes how you want the view is to be layout.
The view has to be smarter than in the MVP case ha it has to understand the structure given from the ViewMOdel to understand what draw.
key difference is the comunicaition patter.
- MVP the presenter tell eplicitely set this label to "x" set the button to green ....
- MVVM the VM just tells the view has to change, the  view goes to the VM and read all the property to re-draw.

# Clean architecture
arhitecture removed dependency of third party dependencies, the onion (clean) architecture allows to separate business logic/entities form implementaiton details.

## SOLID
- single responsability 
- Open close principle: open to extension close to modification 
- Liskov replacement prinple 
- Interface segration principles
- Dependency inversion principle

### Dependency inversion principle
High level code shuld not depends on low level implementaiton 
