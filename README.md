# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM
server
```
import socket

s = socket.socket()
s.bind(('localhost', 12345))
s.listen(1)

print("Waiting for client...")
c, addr = s.accept()
print("Client connected")

while True:
    msg = c.recv(1024).decode()
    print("Client:", msg)

    if msg == "exit":
        break

    reply = input("Server: ")
    c.send(reply.encode())

    if reply == "exit":
        break

c.close()
s.close()
```
client
```
import socket

s = socket.socket()
s.connect(('localhost', 12345))

while True:
    msg = input("Client: ")
    s.send(msg.encode())

    if msg == "exit":
        break

    reply = s.recv(1024).decode()
    print("Server:", reply)

    if reply == "exit":
        break

s.close()
```

## OUPUT
<img width="658" height="272" alt="image" src="https://github.com/user-attachments/assets/f2416eca-b955-453f-9b30-c400ede41803" />
<img width="686" height="212" alt="image" src="https://github.com/user-attachments/assets/9908055c-8408-47a5-88ff-bd9a605d9385" />

## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
