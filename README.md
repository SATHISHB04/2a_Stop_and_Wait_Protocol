# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
### server.py
```python
import socket
s=socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
c,addr=s.accept()
while True:
    i=input("Enter a data: ")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()   
        break
```
### client.py
```python
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT

![Screenshot 2025-04-14 095840](https://github.com/user-attachments/assets/a3415b0d-53c3-4c40-ab89-80a6edf81011)

![Screenshot 2025-04-14 095859](https://github.com/user-attachments/assets/03bed8a6-002e-45a5-ac8c-10979bbd6554)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
