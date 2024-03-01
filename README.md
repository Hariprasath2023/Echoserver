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
### SERVER CODE: echo-server.py:
```
import socket
HOST = "127.0.0.1"  # Standard loopback interface address (localhost)
PORT = 65432  # Port to listen on (non-privileged ports are > 1023)
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
```

### CLIENT CODE: echo-client.py:
```
import socket
HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Hello, world")
    data = s.recv(1024)
print(f"Received {data!r}")
```

## OUTPUT:
### SERVER OUTPUT:
![Screenshot 2024-03-01 111501](https://github.com/Hariprasath2023/Echoserver/assets/145207783/5e05df0e-8639-4c9a-83f0-898b90573546)



### CLIENT SIDE:
![Screenshot 2024-03-01 111447](https://github.com/Hariprasath2023/Echoserver/assets/145207783/b79616d4-117e-4db8-ac72-42db7a0b0924)



## RESULT:
The program is executed successfully
