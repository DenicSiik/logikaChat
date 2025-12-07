# LogikaChat
A simple chat client with **customtkinter** library, featuring a sliding menu, adaptive UI layout & real time messaginh through TCP sockets

## Features
-  **Real time messaging using Python sockets**
-  **customtkinter interface with modern UI**
-  **Fully adaptive UI automatically adjusts to window size**

## How it Works
- **On startup, the client connects to `localhost:8080`**
- **Sends a "joined the chat" message**
- **Listens for messages on a daemon thread**
- **Displays new messages instantly**

## Requirements
```
  customtkinter
  ```
    Python v3.0.0 or more
  ```
  ```
    Server
  ```
```
& more than 5 iq

## Launching
```
  python logikaChat.py
```

## File functions
- `show_menu()` : controls menu
- `menu_anim()` : smooth animation for menu
- `send_message()` : sends user messages to the server
- `get_messages()` : listens to incoming messages and displays them
- `adaptive_UI()` : scales the UI to your device
