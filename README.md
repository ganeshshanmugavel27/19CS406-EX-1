# STUDY OF SOCKET PROGRAMMING WITH CLIENT-SERVER MODEL

# EXP: 1

# DATE :08-03-2023

# AIM :
## To write a python program to perform stop and wait protocol
# ALGORITHM :
## 1. Start the program.
## 2. Get the frame size from the user
## 3. To create the frame based on the user request.
## 4. To send frames to server from the client side.
## 5. If your frames reach the server it will send ACK signal to client otherwise it will sendNACK signal to client.
## 6. Stop the program

# CLIENT PROGRAM :
PYTHON 3

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

# SERVER PROGRAM : 
PYTHON 3
import socket
s=socket.socket()
s.connect(('localhost',8080))
while True:
	print(s.recv(1024).decode())
	s.send("Recieved".encode())


# CLIENT OUTPUT : 
![1](https://github.com/sujathamohankumar/19CS406-EX-1/assets/122046208/59fc3801-4a52-4cd8-b81a-7bbc150236d4)



# SERVER OUTPUT :
![2](https://github.com/sujathamohankumar/19CS406-EX-1/assets/122046208/c5963fe1-aeb8-426f-9bd8-6fd3bb5dd3c1)





# RESULT:
## Thus, python program to perform stop and wait protocol was successfully executed.
