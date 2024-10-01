Flutter Calculator App with Bloc
Overview
This project is a basic Calculator App built using Flutter and Bloc for state management. It demonstrates how to separate the business logic from the UI using the Bloc pattern, enabling a clean, scalable, and testable architecture. The app supports basic arithmetic operations, such as addition, subtraction, multiplication, and division, as well as other functionalities like decimal input and clearing the calculation.

Features
Number Input: Buttons for numbers 0-9 to input numerical values.
Basic Arithmetic Operations: Handles +, -, ×, and ÷ operations.
Decimal Input: Allows entering decimal numbers using the . button.
Clear (C): Resets the input and the result.
Equals (=): Computes the result of the input expression.
Real-Time Display: The current input expression and result are displayed dynamically.
App Architecture
This app uses the Bloc pattern to manage its state, separating the business logic (i.e., the calculation logic) from the UI. This allows for a more organized codebase and easier maintainability.

Key Concepts of Bloc:
Event: Actions dispatched by the user (e.g., pressing a number or an operator button).
State: The output of the Bloc that reflects the current state of the app (e.g., the input and result).
Bloc: Manages the flow of events and the state, handling the calculation logic.
Bloc Components:
CalculatorBloc: The core component managing the calculator's logic and handling events to update the state.
CalculatorState: Holds the current input (equation) and result.
CalculatorEvent: Represents user interactions, such as pressing a number, operator, or equals button.
Folder Structure
bash
Copy code
lib/
│
├── bloc/
│   ├── calculator_bloc.dart      # Bloc that handles the calculator logic
│   ├── calculator_event.dart     # Defines calculator events (e.g., number pressed, operator pressed)
│   └── calculator_state.dart     # Defines the calculator state (input and result)
│
├── screens/
│   └── calculator_screen.dart    # UI of the calculator app
│
└── main.dart                     # Entry point of the app
Bloc Flow
User Interaction: The user presses a button on the calculator (e.g., a number, operator, or equals).
Event Dispatch: An event is dispatched (e.g., NumberPressed, OperatorPressed, EqualsPressed, ClearPressed).
Bloc Logic: The CalculatorBloc processes the event and updates the state (e.g., updates the input expression or calculates the result).
State Update: The UI listens to state changes using BlocBuilder and updates the display accordingly.
How It Works
1. CalculatorBloc
This is where all the business logic resides. It listens for events like number presses, operator presses, and equals, and updates the state accordingly.

dart
Copy code
class CalculatorBloc extends Bloc<CalculatorEvent, CalculatorState> {
  // Business logic here...
}
2. CalculatorState
Holds the current input (equation) and result to be displayed on the UI.

dart
Copy code
class CalculatorState {
  final String result;
  final String input;
  // Current state structure here...
}
3. CalculatorEvent
Defines all possible actions that the user can perform, such as pressing numbers, operators, equals, or clear.

dart
Copy code
abstract class CalculatorEvent {}

class NumberPressed extends CalculatorEvent {
  final String number;
}

class OperatorPressed extends CalculatorEvent {
  final String operator;
}

// Other events...
4. CalculatorScreen
The UI uses a grid layout to display buttons for numbers, operators, and special buttons like Clear and Equals. It listens for state changes using BlocBuilder and updates the display in real-time.

dart
Copy code
class CalculatorScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      // UI layout and buttons here...
    );
  }
}
Button Layout
7	8	9	÷
4	5	6	×
1	2	3	-
0	.	=	+
C			
Dependencies
This app uses the following Flutter packages:

flutter_bloc: Implements the Bloc pattern in Flutter for managing state.
bloc: Provides the core functionality for the Bloc pattern.
Add these dependencies to your pubspec.yaml:

yaml
Copy code
dependencies:
  flutter:
    sdk: flutter
  flutter_bloc: ^8.0.0
  bloc: ^8.0.0
Setup Instructions
Prerequisites
Make sure you have Flutter installed. You can check this by running:


![image](https://github.com/user-attachments/assets/f4fad29c-9c92-4677-be9f-f133de92d3da)


bash
Copy code
flutter --version
Getting Started
Clone the repository:

bash
Copy code
git clone https://github.com/yourusername/flutter-calculator-bloc.git
Navigate to the project directory:

bash
Copy code
cd flutter-calculator-bloc
Install the dependencies:

bash
Copy code
flutter pub get
Run the app:

bash
Copy code
flutter run
How to Use
Input numbers: Use the number buttons (0-9) to input numbers.
Perform operations: Use the +, -, ×, and ÷ buttons to perform arithmetic operations.
Clear input: Press the C button to clear the input and result.
Compute result: Press = to compute the result of the input expression.
Use decimal numbers: Use the . button to input decimal numbers.
Conclusion
This Flutter Calculator App demonstrates how to use the Bloc pattern to manage state in a clean, maintainable, and scalable way. It shows how to separate business logic from UI and how to manage user input, operations, and results effectively.

License
This project is licensed under the MIT License.
