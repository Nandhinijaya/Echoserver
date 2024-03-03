# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:
## ECHO SERVER.py
```
import socket

HOST = '127.0.0.1'  # Standard loopback interface address (localhost)
PORT = 65432        # Port to listen on (non-privileged ports are > 1023)

def echo_server():
    with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
        s.bind((HOST, PORT))
        s.listen()
        print(f"Echo server listening on {HOST}:{PORT}")
        conn, addr = s.accept()
        with conn:
            print(f"Connected to {addr}")
            while True:
                data = conn.recv(1024)
                if not data:
                    break
                conn.sendall(data)

if __name__ == "__main__":
    echo_server()

```
## ECHO CLIENT.py
```
import socket

HOST = '127.0.0.1'  # The server's hostname or IP address
PORT = 65432        # The port used by the server

def echo_client(message):
    with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
        s.connect((HOST, PORT))
        s.sendall(message.encode())
        data = s.recv(1024)
        print(f"Received from server: {data.decode()}")

if __name__ == "__main__":
    message = input("Enter message to send to server: ")
    echo_client(message)

```

## OUTPUT:
## SERVER:
![server](https://github.com/Nandhinijaya/Echoserver/assets/121998147/3e4956be-1538-49cf-841f-dc95675d549f)

## CLIENT:

![client](https://github.com/Nandhinijaya/Echoserver/assets/121998147/f4c96408-44da-4c44-bb6a-8cae2df8883a)

## RESULT:
The program is executed successfully
