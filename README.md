# How to Architect a Production-Level App in Flutter

Domain-Driven Design architecture

    Domain: The layer where your model classes, custom failure classes, and interfaces exist (e.g. user_model.dart).

    Infrastructure: The layer that implements the interfaces you defined in the Domain layer (e.g. firebase_auth_service.dart).

    Application: The business logic and state management are handled in this layer (e.g. auth_cubit.dart).

    Presentation: The UI of your app. The presentation layer is where your Widgets reside (e.g. sign_in_page.dart).
    
# State management 

Challenges of BLoC

    It requires excessive boilerplate even for simple state management.

    It is difficult to understand/follow when the state is going to be updated as the yieldcommand works asynchronously.

    Bloc-to-bloc communication is difficult. yield command does not work as expected when you call it from an inner scope.

Advantages of Cubit

  There are many advantages of choosing Cubit over Bloc. The two main benefits are:
  
    Cubit is a subset of Bloc; so, it reduces complexity. Cubit eliminates the event classes.
    
    Cubit uses emitrather than yield to emit state. Since emit works synchronously, you can ensure that the state is updated in the next line.
