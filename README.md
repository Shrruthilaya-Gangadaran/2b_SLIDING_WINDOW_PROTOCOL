<H1 ALIGN=CENTER> SLIDING WINDOW PROTOCOL </H1>
<H3> NAME : SHRRUTHILAYA G </H3>
<H3> REGISTER NUMBER : 212221230097 </H3>
<H3>EXPERIMENT NO : 02 B </H3>
<H3>DATE  : 11.05.2024 </H3>

## AIM:
To develop a python code to implement sliding window protocol.

## ALGORITHM:
1. Start the program.
2. Get the frame size from the user.
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client.
6. Stop the Program.

## PROGRAM:
### CLIENT:
```python
import socket
s = socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c, addr = s.accept()
size = int(input("Enter number of frames to send : "))
l = list(range(size))
s = int(input("Enter Window Size : "))
st = 0
i = 0
while True:
    while(i<len(l)):
        st += s
        c.send(str(l[i:st]).encode())
        ack = c.recv(1024).decode()
        if ack:
            print(ack)
            i += s
```
### SERVER:
```python
import socket
s = socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received from the server".encode())
```
## OUTPUT:
### CLIENT:
![output1](https://github.com/Shrruthilaya-Gangadaran/2b_SLIDING_WINDOW_PROTOCOL/assets/93427705/f2806089-90fa-443e-bb6c-a6ffa4f622ef)

### SERVER:
![output2](https://github.com/Shrruthilaya-Gangadaran/2b_SLIDING_WINDOW_PROTOCOL/assets/93427705/2272a168-15f9-4476-879c-9d36c828e39a)

## RESULT:
Thus, the implementation of sliding window protocol is done successfully.

