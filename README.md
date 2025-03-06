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
## ECHO SERVER.PY
```
import socket


HOST = "192.168.242.229"# Standard loopback interface address (localhost)
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
## ECHO CLIENT.PY
```
import socket


HOST = "192.168.242.229"  # The server's hostname or IP address
PORT = 65432  # The port used by the server


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"MANOGARAN 212223240081")
    data = s.recv(1024)


print(f"Received {data!r}")






```
## OUTPUT:
## ECHO SERVER:
![Screenshot 2025-03-06 114015](https://github.com/user-attachments/assets/4bfb0409-64db-4504-bf27-d5dcf96651d4)

## ECHO CIENT:
![Screenshot 2025-03-06 114003](https://github.com/user-attachments/assets/6735fa0a-abbd-4e2f-b372-71639a0d2f06)

## RESULT:
The program is executed successfully
