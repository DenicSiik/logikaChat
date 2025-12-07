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
```
  Python v3.0.0 or more
```
  Server
  You can use this -
```
  import socket
import threading

HOST = '0.0.0.0'
PORT = 8080 # 0 - 1000

clients = []

def broadcast(data, exclude_socket=None): # data = привіт
    for client in clients:
        if client != exclude_socket:
            try:
                client.sendall(data)
            except:
                pass

def handle_client(client_socket):
    while True:
        try:
            data = client_socket.recv(4096) # привіт
            if not data:
                break
            broadcast(data, exclude_socket=client_socket)
        except:
            break
    if client_socket in clients:
        clients.remove(client_socket)
    client_socket.close()

def main():
    server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM) # IPv4 127.0.0.1, TCP
    server_socket.setsockopt(socket.SOL_SOCKET, socket.SO_REUSEADDR, 1)
    server_socket.bind((HOST, PORT))
    server_socket.listen(5)
    print(f"Сервер запущено на {HOST}:{PORT}")
    while True:
        client_socket, addr = server_socket.accept()
        print(f"Підключився клієнт: {addr}")
        clients.append(client_socket)
        t = threading.Thread(target=handle_client, args=(client_socket,))
        t.start()

main()
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
