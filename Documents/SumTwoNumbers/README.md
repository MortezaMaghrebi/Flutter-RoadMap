## Sum Calculator - Flutter App (README.md)

This repository contains a simple Flutter app that calculates the sum of two user-provided numbers.

**Getting Started**

1.  **Clone the repository:** Use `git clone https://github.com/your-username/sum-calculator.git` to clone this repository locally.
2.  **Run the app:** Make sure you have Flutter installed (see [Flutter download](https://flutter.dev/docs/get-started/install)). Navigate to the project directory in your terminal and run `flutter run`. This will launch the app on your connected device or emulator.

**Understanding the Code**

The code for this app is located in the `main.dart` file. Let's break down the key functionalities:

1. **Importing Flutter:**
   ```dart
   import 'package:flutter/material.dart';
   ```
   This line imports the Flutter library, providing the building blocks for creating the app's UI.

2. **The `main` Function:**
   ```dart
   void main() {
     runApp(MyApp());
   }
   ```
   This is the entry point of the app. It calls `runApp` with an instance of `MyApp`, essentially launching the app.

3. **The `MyApp` Class:**
   - `MyApp extends StatefulWidget`: This defines a stateful widget that can change its appearance based on user interaction.

4. **State Management:**
   - `_MyAppState extends State<MyApp>`: This connects the `MyApp` widget with its internal state (`_MyAppState`).

5. **Text Editing Controllers:**
   ```dart
   final firstNumberController = TextEditingController();
   final secondNumberController = TextEditingController();
   ```
   These controllers manage the text entered by the user in the two textboxes for numbers.

6. **Variable for Sum:**
   ```dart
   double sum = 0.0;
   ```
   This variable stores the calculated sum of the two numbers.

7. **`calculateSum` Function:**
   ```dart
   void calculateSum() {
     // ... code to convert text to numbers and calculate sum ...
     setState(() {
       sum = firstNumber + secondNumber;
     });
   }
   ```
   This function retrieves the text from the controllers, converts them to doubles (handling potential errors), calculates the sum, and updates the `sum` variable using `setState`. This triggers a UI rebuild to display the updated sum.

8. **Building the UI (`build` method):**
   This method defines the app's user interface using various widgets.

9. **Scaffold - The Main Layout:**
   ```dart
   return MaterialApp(
     home: Scaffold(
       // ... app elements go here ...
     ),
   );
   ```
   The `Scaffold` widget provides a basic app structure with an optional app bar and a body for the main content.

10. **UI Elements:**
   - `AppBar`: Creates the top bar with the title "Sum Calculator".
   - `Padding`: Adds padding around the content within the body.
   - `Column`: Arranges UI elements vertically.
   - `TextField`: Two textboxes for user input, using the controllers.
   - `ElevatedButton`: The "Calculate" button that triggers the `calculateSum` function.
   - `Text`: Displays the calculated sum with a label "Sum:".

**Additional Notes**

- The code uses the `keyboardType: TextInputType.number` property on the text fields to optimize the keyboard for numerical input.
- Remember to save any changes you make to the `main.dart` file and then run `flutter run` again to see the updated app.

This is a basic example to showcase a simple Flutter application with user input and state management. Feel free to explore further and build more complex functionalities!

