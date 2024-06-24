## Login/SignUp - Flutter App 

 This is a login application written in Flutter. It allows users to login with an existing account or sign up for a new account.

**Dart**

```dart
import 'package:argfood/models/user_model.dart';
import 'package:flutter/material.dart';

class User{
   int? id;
   String username;
   String password;
   User({required this.username,required this.password,this.id});
}

void main() {
  runApp(MyApp());
}

class MyApp extends StatefulWidget {
  @override
  State<MyApp> createState() => _MyAppState();
}

class _MyAppState extends State<MyApp> {
  // Text editing controllers for the textboxes
  final userNameController = TextEditingController();
  final passwordController = TextEditingController();

  //List of users
  List<User> users = [];

  // Variable to store the sum
  String loginResult = "";
  Color loginInfoColor = Colors.green;

  // Function to respond to the login button
  void Login() {
    setState(() {
      bool userexist = false;
      for (int i = 0; i < users.length; i++) {
        if (users[i].username == userNameController.text &&
            users[i].password == passwordController.text) {
          userexist = true;
          break;
        }
      }
      if (!userexist) {
        loginResult = "User not exist!";
        loginInfoColor = Colors.red;
      } else {
        loginResult = "Login Seucceeded";
        loginInfoColor = Colors.green;
      }
    });
  }

  // Function to respond to the SignUp textbutton
  void SignUp() {
    setState(() {
      if (userNameController.text.length < 4) {
        loginResult = "Username must be at least 4 characters";
        loginInfoColor = Colors.red;
      } else if (passwordController.text.length < 4) {
        loginResult = "Password must be at least 4 characters";
        loginInfoColor = Colors.red;
      } else {
        User user = User(
            username: userNameController.text,
            password: passwordController.text);
        users.add(user);
        loginResult = "Sign Up Seucceeded";
        loginInfoColor = Colors.green;
      }
    });
  }

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: const Text('Login Page'),
        ),
        body: Padding(
          padding: const EdgeInsets.all(20.0),
          child: Column(
            children: [
              const SizedBox(height: 20.0),
              CircleAvatar(
                radius: 120.0,
                backgroundColor: Colors.transparent,
                backgroundImage: AssetImage("../assets/images/profile.png"),
              ),
              const SizedBox(height: 10.0),
              TextField(
                controller: userNameController,
                keyboardType: TextInputType.number,
                decoration: const InputDecoration(
                  labelText: 'User Name',
                ),
              ),
              const SizedBox(height: 10.0),
              TextField(
                controller: passwordController,
                keyboardType: TextInputType.number,
                decoration: const InputDecoration(
                  labelText: 'Password',
                ),
              ),
              const SizedBox(height: 20.0),
              SizedBox(
                width: 150,
                height: 40.0,
                child: ElevatedButton(
                  onPressed: Login,
                  child: const Text('Login'),
                ),
              ),
              const SizedBox(height: 10.0),
              TextButton(
                onPressed: SignUp,
                child: Text('Sign Up'),
              ),
              const SizedBox(height: 40.0),
              Text(
                '$loginResult',
                style: TextStyle(fontSize: 14.0, color: loginInfoColor),
              ),
            ],
          ),
        ),
      ),
    );
  }
}

```

**Adding the Assets Folder:**

- Create a new folder named `assets` inside your project directory and create a new folder named `images` inside the `assets` folder.

**3. Copying the Image:**

- Obtain the image you want to use (profile picture in this example).
- Copy the image file and paste it inside the newly created `images` folder.
- Rename the image to `profile.png`

- Make sure the image format is compatible with Flutter (commonly used formats are PNG, JPEG, and WebP).

**Remember:** After making changes, you need to run `flutter pub get` in your IDE terminal to download any required dependencies.

**Here's a breakdown of the code:**

1. **Importing packages:**
   - `import 'package:argfood/models/user_model.dart';`: This line imports the `User` model class from the `argfood/models` directory. This class likely defines the structure of a user object, including properties like username and password.
   - `import 'package:flutter/material.dart';`: This line imports the Flutter material library, which provides the foundation for building user interfaces in Flutter apps.

2. **The `main` function:**
   - `void main() {runApp(MyApp());}`: This is the entry point of the application. It calls the `runApp` function from the Flutter package to start the app and displays an instance of the `MyApp` class.

3. **The `MyApp` class:**
   - This class represents the main application widget. It inherits from the `StatefulWidget` class, which indicates that the widget has an internal state that can change over time.

4. **The `_MyAppState` class:**
   - This class is the state class for the `MyApp` widget. It manages the state of the widget, which includes the values of the text fields, the list of users, the login result message, and the color of the login info text.

   - **State variables:**
     - `final userNameController = TextEditingController();`: This creates a text editing controller for the username text field. The text editing controller is used to manage the text entered by the user in the text field.
     - `final passwordController = TextEditingController();`: This creates a text editing controller for the password text field.
     - `List<User> users = [];`: This creates an empty list to store the users who have signed up for the application.
     - `String loginResult = "";`: This variable stores the message to be displayed to the user after they attempt to login or sign up.
     - `Color loginInfoColor = Colors.green;`: This variable stores the color of the login info text. It is initially set to green.

   - **Functions:**
     - `void Login() { ... }`: This function is called when the user taps the "Login" button. It iterates through the list of users to check if the username and password entered by the user match the credentials of any existing user. If a match is found, the `loginResult` message is set to "Login Successful" and the `loginInfoColor` is set to green. Otherwise, the `loginResult` message is set to "User not exist!" and the `loginInfoColor` is set to red. The `setState` function is used to update the state of the widget, which triggers the UI to rebuild with the new values of the login result message and the color of the login info text.
     - `void SignUp() { ... }`: This function is called when the user taps the "Sign Up" text button. It checks if the username and password entered by the user are at least 4 characters long. If they are not, the `loginResult` message is set to an appropriate error message and the `loginInfoColor` is set to red. Otherwise, a new `User` object is created with the username and password entered by the user, and it is added to the list of users. The `loginResult` message is then set to "Sign Up Successful" and the `loginInfoColor` is set to green. The `setState` function is used to update the state of the widget, which triggers the UI to rebuild with the new values of the login result message and the color of the login info text.

5. **The `build` method:**
   - This method is called whenever the state of the widget changes. It is responsible for building the user interface of the application.

   - **The user interface:**
     - The user interface consists of a Scaffold widget, which is the basic structure for most Flutter apps.
     - The Scaffold widget has an AppBar at the top, which displays the title of the app ("Login Page" in this case).
     - The body of the Scaffold is a padded container that contains a Column widget.
     - The Column widget contains several child widgets, including:
       - A CircleAvatar widget that displays a profile picture image.
       - Two text field widgets for the username and password.
       - An ElevatedButton widget for the "Login" button.
       - A TextButton widget for the "Sign Up" text button.
       - A Text widget that displays the login result message.
