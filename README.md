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
client
~~~
import socket
s=socket.socket()
s.bind(('localhost',8000))
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
~~~

server
~~~
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())

~~~


## OUTPUT

client

![361639442-3d9c27ef-7cac-4e08-9450-09022c8718ee](https://github.com/user-attachments/assets/3c5e982e-219f-4192-b3cc-30846800dcce)

server

![361639967-78dcca97-def0-4d62-b970-4737bf68721c](https://github.com/user-attachments/assets/7df09e6b-68c1-420d-9aa2-3b3d805e1a6c)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
