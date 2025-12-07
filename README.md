# LogikaChat
A simple chat client with **customtkinter** library, featuring a sliding menu, adaptive UI layout & real time messaginh through TCP sockets

## Features
-  **Real time messaging** using Python sockets
-  **customtkinter interface** with modern UI
-  **Fully adaptive UI** automatically adjusts to window size

## How it Works
- **On startup, the client connects to `localhost:8080`**
- **Sends a "joined the chat" message**
- **Listens for messages on a daemon thread**
- **Displays new messages instantly**

## Requirements
```
  customtkinter
```
& more than 5 iq

## Launching
```
  pythin logiChat.py
```
