# Flutter Signup Form - MAD 4360 In-Class Activity 09

A Flutter signup screen built for MAD 4360 (Mobile App Development). Demonstrates StatefulWidget, form validation, screen navigation, and animations.

## Features

- **Signup Form**: Name, Email, and Password fields with an `OutlineInputBorder` and prefix icons
- **Input Validation**: Inline validators that show red error messages on empty or invalid input

## Bonus Challenges Completed

- **Confirm Password**: Second password field that validates both values match
- **Avatar Picker**: Emoji selector that lets users choose a profile avatar before signing up
- **Screen Navigation**: Successful signup navigates to a `WelcomeScreen` via `Navigator.push` and `MaterialPageRoute`
- **Celebratory Animation**: `WelcomeScreen` fades in and scales up with an elastic bounce using `AnimationController`

## Widget Tree

```
MyApp (StatelessWidget)
└── MaterialApp
    └── SignupPage (StatefulWidget)
        └── Scaffold
            └── Form (keyed with GlobalKey<FormState>)
                └── Column
                    ├── Avatar Picker
                    ├── TextFormField (Name)
                    ├── TextFormField (Email)
                    ├── TextFormField (Password)
                    ├── TextFormField (Confirm Password)
                    └── ElevatedButton -> WelcomeScreen
```

## How to Run

```bash
flutter pub get
flutter run
```

## Testing Checklist

- Leave fields empty and tap Sign Up -> expect error messages
- Enter an email without `@` -> expect email error
- Enter a password shorter than 6 characters -> expect password error
- Enter mismatched passwords -> expect confirm password error
- Fill all fields correctly -> navigates to WelcomeScreen with fade-in animation

## Project Structure

```
lib/
└── main.dart       # MyApp, SignupPage, WelcomeScreen
```
