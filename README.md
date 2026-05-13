## TYT (Test Your Typing) v2.0
## Live at: https://ah74n.github.io/tyt/

TYT is a responsive, frontend-only typing speed tester built entirely with vanilla HTML, CSS, and JavaScript. It focuses on a clean UI, accurate performance metrics, and a highly responsive typing feel.

##  Under the Hood
Zero-Latency Audio: To mimic the authentic feel of a mechanical keyboard, the app bypasses standard HTML <audio> tags. Instead, it leverages the Web Audio API (AudioContext). The keystroke sound is fetched and decoded into a memory buffer on load. This allows for rapid, overlapping audio playback with randomized pitch shifts, ensuring zero lag or audio dropouts even if you type at 150+ WPM.

## Dynamic Theming:  
The app features a multi-theme engine (Dark, Light, Matrix, Dracula) built entirely on CSS Custom Properties. Selecting a theme updates the data-theme attribute on the <body> tag, which instantly swaps the global color palette. The chosen theme is cached in localStorage so it persists across different pages and sessions.

## Metrics & State:

WPM Calculation: Speed is calculated using the standard typographical metric where one "word" equals 5 characters. The engine calculates the final WPM strictly based on the time elapsed using the formula: (Total Characters Typed / 5) / Time Elapsed in Minutes.

Accuracy: Tracked by cross-referencing the user's input array against the target string array in real-time: ((Total Characters - Errors) / Total Characters) * 100.

State Management: Since the app uses a multi-page architecture, localStorage acts as the central state manager to pass user configurations (name, difficulty, selected time) to the test engine, and route the final scores to the results dashboard.
