import os
import webbrowser
import platform
import time

# Detect system (Windows/Linux/Android/Mac)
system_name = platform.system().lower()

# === Define Actions ===
def open_screen_panel():
    """Opens file manager or current folder."""
    if "android" in system_name or "linux" in system_name:
        os.system("xdg-open .")
    elif "windows" in system_name:
        os.system("explorer .")
    elif "darwin" in system_name:
        os.system("open .")
    print("✅ Screen Panel opened\n")

def open_search_engine():
    """Opens Google search."""
    webbrowser.open("https://www.google.com")
    print("✅ Search Engine opened\n")

def open_code_hub():
    """Opens coding platforms."""
    webbrowser.open("https://github.com")
    webbrowser.open("https://replit.com")
    print("✅ Code Hub opened\n")

def open_game_hub():
    """Opens game platforms."""
    webbrowser.open("https://store.steampowered.com")
    webbrowser.open("https://itch.io")
    print("✅ Game Hub opened\n")

# === Menu Display ===
def menu():
    print("""
🚀 JOSECOM Shortcut Manager
-----------------------------------
1️⃣  Open Screen Panel
2️⃣  Open Search Engine
3️⃣  Open Code Hub
4️⃣  Open Game Hub
0️⃣  Exit
-----------------------------------
""")

# === Main Loop ===
while True:
    menu()
    choice = input("👉 Enter your choice (0-4): ").strip()

    if choice == "1":
        open_screen_panel()
    elif choice == "2":
        open_search_engine()
    elif choice == "3":
        open_code_hub()
    elif choice == "4":
        open_game_hub()
    elif choice == "0":
        print("👋 Exiting Shortcut Manager. Goodbye!")
        time.sleep(1)
        break
    else:
        print("❌ Invalid choice! Try again.\n")
