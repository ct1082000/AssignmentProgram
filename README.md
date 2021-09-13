# Bulletin Board System - Client Side

CS3201 Programming Assignment <br />

//You must make it clear how to compile and run your code by explaining it in your readme text file. The development environment should also be indicated in this file. //
 
## Description
This project aims to build the client side of the Bulletin Board System, which performs the text exchange between the client and server.  <br />
In this project, the server program is provided and its default port number is 16000 running on IP address 192.168.0.1. There are three commands which are POST, READ and QUIT, executed by the client for the communication to the server. <br />

## Development Enviornment 
This program is developed in JAVA languagae under MS Windows with two computers. The IDE of the program is the Visual Studio Code. Besides, Github connected to the IDE is used for the share of code. <br />

## Building Process
In this program, the library 'java.net' is mainly used for the function of the client. <br /><br />

To establish the connection between the client and server, the java class Socket is implemented. 
After setting the default port number 16000, the Socket is built through accepting the port and inputted ip address. 
Thus, there is the isconnected() function of the Socket class to return the connection status from the server if the connection is sucessful. 
If the value is true, the "Connection status: success" is printed, else "Connection status: failed" is printed.<br /><br />

After the connection is established, there is a switch case to accept the inputted command in client. 
The readable command is "POST", "READ", and "QUIT" which is case sensitive. 
If one character of the command is small letter, the inputted command is considered as a failed case and cannot be sent to the server. <br />

For "POST": <br />
There is a do-while loop to let the user input the texts. 
The program will continue read the user input if the input length is equal or larger than 1. The command is stored in the postInput string. In every loop, the inputted message is stored in the postInput string seperated by "\n" as well.
When the users type only one "." in a single line, the program will send all the typed texts which are stored in the postInput before the "." to server.
Finally, the command and mesaages posted by client are read by server via the PrintWriter class which is socket.getOutputStream() as the output stream. 

For "READ":
The command is read by the PrintWriter class which is socket.getOutputStream() as the output stream. And the server sends all the messages posted by client by the function receiveServer(), which will send the char array storing the posted messages and the reponse from server "OK" or ".". 

For "QUIT":
The command is read by the PrintWriter class which is socket.getOutputStream() as the output stream. And the quit status becomes false and quit the while loop, going to finally{} which contains the function socket.close(). The client program closes.

## How to compile and run






