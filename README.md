# 19CS406-EX-1 STUDY OF SOCKET PROGRAMMING WITH CLIENT-SERVER MODEL

DATE :

AIM :

To write a python program to perform stop and wait protocol

ALGORITHM :

1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client otherwise it will sendNACK signal to client.
6. Stop the program



PROGRAM :

CLIENT PROGRAM :

import socket
s=socket.socket()
s.bind(('localhost',8080))
s.listen(5)
c,addr=s.accept()
while True:
	i=input("ENter a data:")
	c.send(i.encode())
	ack=c.recv(1024).decode()
	if ack:
		print(ack)
		continue
	else:
		c.close()
		break

SERVER PROGRAM :

import socket
s=socket.socket()
s.connect(('localhost',8080))
while True:
	print(s.recv(1024).decode())
	s.send("Recieved".encode())

CLIENT OUTPUT :

![1](https://github.com/sujathamohankumar/19CS406-EX-1/assets/122046208/fc578e1c-f9b6-4c00-abf8-64acd0af3765)


SERVER OUTPUT :

![2](https://github.com/sujathamohankumar/19CS406-EX-1/assets/122046208/07e64486-4c53-4f84-8cef-d72d632876a9)

 
RESULT:
