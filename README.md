# Flutter App Lifecycle States

![Flutter App Lifecycle Diagram](https://miro.medium.com/v2/resize:fit:720/format:webp/1*YNTT8WK-CUWxUHBbhKJPpQ.png)

Flutter applications move through several lifecycle states as they run. Understanding these states helps you manage resources, save data, and handle interruptions correctly.

---

## 1. Resumed

- **Description:**  
  The app is in the foreground. It is visible, has focus, and responds to user input.
- **Meaning:**  
  This is the **normal running state** of the app.

---

## 2. Inactive

- **Description:**  
  The app is in a transition state. It is still visible but has lost user focus.
- **Common Scenarios:**
    - Incoming phone call
    - System dialog (e.g., low battery alert)
    - Entering split-screen mode
- **Platform Behavior:**
    - On iOS, this often occurs when the user swipes up to show the App Switcher.

---

## 3. Hidden

- **Description:**  
  A state between **Inactive** and **Paused**.
- **Purpose:**  
  Indicates the app is no longer visible but hasn’t been fully paused by the engine.
- **Scenario:**  
  When the app is fully minimized or the user switches to another app, it briefly enters this state.

---

## 4. Paused

- **Description:**  
  The app is not visible and runs in the background.
- **Behavior:**
    - The app remains in memory
    - System may restrict execution to save battery
- **Best Practice:**  
  Save user data and pause ongoing timers or animations here.

---

## 5. Detached

- **Description:**  
  The app is hosted by a Flutter engine but detached from any UI.
- **Scenarios:**
    - Just before the app is destroyed
    - Flutter engine running without a UI (e.g., background service)
- **Important Note:**  
  Do **not** rely on this state for saving data—the process may be killed immediately.

---