# Implicit Intents – Android App

## About the Project

This project was developed as part of **Mobile Application Development**. The goal is to create an Android application that demonstrates the use of implicit intents to interact with other applications and Android system components.

The application allows users to open websites in a web browser, search for locations using a map application, and share text through available sharing applications.

The application is developed in **Java** using **Android Studio**, with the user interface defined in XML.

## Features

- Three separate input fields:
  - Website URL – Accepts a web address to open in a browser.
  - Location – Accepts a location name to display on a map.
  - Text – Accepts text to share with other applications.
- Three corresponding buttons:
  - `Open Website` – Opens the entered URL using an application capable of handling web links.
  - `Open Location` – Searches for the entered location using a map application.
  - `Share This Text` – Opens the Android sharing interface to share the entered text.
- Implicit intent handling using `Intent.ACTION_VIEW`.
- Validation to check whether the system can handle an intent before launching it.
- Text sharing using `ShareCompat.IntentBuilder`.
- MIME type `text/plain` for sharing text.

## Technologies Used

- **Language:** Java
- **IDE:** Android Studio
- **UI Design:** XML
- **Platform:** Android
- **Components:** Activity, Intent, Uri, EditText, Button, LinearLayout
- **Additional Classes:** `ShareCompat.IntentBuilder`

## Application Structure

The application primarily uses the following files and classes:

- `MainActivity.java` – Handles user input, initializes the input fields, and implements the three implicit intent methods.
- `activity_main.xml` – Defines the main screen layout using a vertically oriented `LinearLayout`, containing three input fields and three buttons.
- `strings.xml` – Contains the string resources used for input hints, button labels, and other interface text.
- `AndroidManifest.xml` – Defines the application configuration and any required intent filters.

## How It Works

1. Launch the application to display `MainActivity`.
2. Enter a website address into the first input field.
3. Tap **Open Website** to launch the entered URL in an appropriate application, usually a web browser.
4. Enter a location name into the second input field.
5. Tap **Open Location** to search for the specified location in an available map application.
6. Enter text into the third input field.
7. Tap **Share This Text** to open the Android sharing interface.
8. Select an available application or sharing destination to share the entered text.

## Implicit Intents

The application uses implicit intents to request actions from the Android operating system without specifying which application must handle them.

### Opening a Website

The `openWebsite(View view)` method reads the URL from the first `EditText` field and converts it into a `Uri` object.

An intent is created using `Intent.ACTION_VIEW`, allowing the Android system to find an appropriate application capable of opening the URL.

Before launching the intent, the application checks whether a suitable activity is available to handle the request.

### Opening a Location

The `openLocation(View view)` method reads the location name from the second input field and constructs a geographic URI using the following format:

```text
geo:0,0?q=location_name
```

The URI is passed to an implicit intent with the action `Intent.ACTION_VIEW`, which requests the system to display the specified location using an available map application.

### Sharing Text

The `shareText(View view)` method reads the text from the third input field and uses `ShareCompat.IntentBuilder` to create a sharing intent.

The MIME type is set to `text/plain`, indicating that the content being shared is plain text.

Android then displays the available applications and destinations that support receiving shared text.

## Installation and Setup

1. Clone this repository:

   ```bash
   git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
   ```

2. Open **Android Studio**.
3. Select **Open** and choose the cloned project folder.
4. Wait for Gradle to finish syncing.
5. Start an Android emulator or connect an Android device.
6. Click **Run** to build and launch the application.

Replace `YOUR-USERNAME` and `YOUR-REPOSITORY` with your GitHub username and repository name.

## Learning Objectives

This assignment provides practical experience with:

- Understanding the difference between explicit and implicit intents.
- Creating implicit intents using `Intent.ACTION_VIEW`.
- Opening external websites using Android intents.
- Working with `Uri` objects and URI schemes.
- Opening geographic locations using `geo:` URIs.
- Checking whether an activity can handle an intent before launching it.
- Sharing plain text between applications.
- Using `ShareCompat.IntentBuilder` to create sharing intents.
- Working with MIME types such as `text/plain`.
- Connecting XML interface elements to Java methods using the `android:onClick` attribute.
- Managing string resources using `strings.xml`.
