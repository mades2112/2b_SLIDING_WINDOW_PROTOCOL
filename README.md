# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
CLIENT:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
   while(i<len(l)):
        st+=s
        c.send(str(l[i:st]).encode())
        ack=c.recv(1024).decode()
        if ack:
           print(ack)
           i+=s
```
SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000)
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
 ```
## OUPUT
client:

![Screenshot 2024-02-28 152132](https://github.com/mades2112/2b_SLIDING_WINDOW_PROTOCOL/assets/152461996/a6982928-9cd5-46c0-b813-e2ee6df9e465)

server:

![Screenshot 2024-02-28 152159](https://github.com/mades2112/2b_SLIDING_WINDOW_PROTOCOL/assets/152461996/d7ed331b-0aaa-4b85-bb7d-c6f00d1cf69e)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
