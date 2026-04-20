# Flutter Signup App - MAD 4360 In-Class Activity 10

A multi-screen Flutter signup app built for MAD 4360 (Mobile App Development). This is Part 2 of 2, extending the validated signup form from Activity 09 into a complete app flow with a welcome screen, enhanced signup screen, and a success screen.

## Built On

Activity 09 established the foundation: a `StatefulWidget` signup form with input validation, avatar selection, confirm password logic, and basic navigation. Activity 10 refactors that work into a cleaner multi-screen structure and adds richer user experience details.

## What Was Added in Activity 10

- **WelcomeScreen**: Animated typewriter intro using `animated_text_kit`, leads into the signup flow
- **Date Picker**: Birth date selection via `showDatePicker` on the signup screen
- **Password Visibility Toggle**: Eye icon to show/hide password and confirm password fields
- **Loading State**: 2-second spinner on the submit button before navigating to success
- **SuccessScreen**: Displays the user's name and avatar, plays a confetti burst using the `confetti` package, uses `pushReplacement` so users cannot navigate back to the form
- **Organized File Structure**: Each screen lives in its own file under `lib/screens/`, keeping `main.dart` minimal

## Packages Used

- `animated_text_kit` - typewriter animation on the welcome screen
- `confetti` - celebration effect on the success screen

## App Flow

```
WelcomeScreen
    |
    | Navigator.push
    v
SignupScreen (form with validation)
    |
    | Navigator.pushReplacement
    v
SuccessScreen (confetti + personalized message)
```

## Project Structure

```
lib/
|- main.dart
|- screens/
    |- welcome_screen.dart
    |- signup_screen.dart
    |- success_screen.dart
```

## How to Run

```bash
flutter pub get
flutter run
```

## Testing Checklist

- Tap Get Started on the welcome screen -> opens signup form
- Leave fields empty and tap Sign Up -> expect inline error messages
- Enter an email without `@` -> expect email error
- Enter a password shorter than 6 characters -> expect password error
- Enter mismatched passwords -> expect confirm password error
- Tap the eye icon -> password text toggles visible/hidden
- Tap Date of Birth -> date picker opens and selection displays
- Fill all fields correctly -> loading spinner shows, then navigates to success screen
- Tap Celebrate Again on the success screen -> confetti replays
- Press back on the success screen -> returns to welcome screen, not the form
