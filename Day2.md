# Day 2
* Connect the Pieces
  * Connect the pieces in a reusable way: The initial responsibilities of the connector
  * Memory Management: Implement the code so it follows the rules for good memory management, and the need for WeakReferences and how to implement them
  * Navigation: How to implement navigation in an advanced architecture
  * Intents: How and where to create the intents and pass information in order to navigate
* Dependency Injection
  * Service Locator (Dagger 2): Use Dagger 2 to perform the dependency injection, implementing in a way that the architecture is fully testable
* Second User Story: Add
  * Organizing the code: How to separate different pieces in packages
  * Presentation vs Domain Logic: The boundaries between the two types of logic and how they affect implementation
  * Immutables: The implications of using immutables to model our data and how to do it, and implementation using reference types
  * Observation: Observation vs flow synchronization and when and how to implement them
* Implement the Third User Story: Detail
  * Identity: The need an importance of identity and how to implement it
  * Command pattern: How the command pattern can be helpful and how to use it


  ## Clean architecture
  The entity gateway abstraction allows to build and test the app before the API are ready. is also useful for a POC as i can prove the idea without spending time in persistance and API but if I get the sign off I just need to swap the persiastance.
  In a secure application always pass a copy never a reference to the entity

  ## Dependency injection
  - constructor
  - property
  - method

  ioc --> don't call me I will call you, the object should provide a method to inject the dependencies.

## Navigation
  In navigation source activity should not have any reference to the destination activity. The intent should be created in a "companion object method" of the destination, in there is should get the data form the source and extract it from the intent.

  View knows HOW to navigate
  ViewModel know Where to navigate in abtraction 
  Connector convert the abstract destination to an actual destination.
