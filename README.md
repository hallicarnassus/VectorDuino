IMU.cpp - VectorNav VN-100 library for Arduino
Code by Luke Nyhof

This code works with boards based on ATMega168/328 and ATMega1280 (Serial port n)
This library is free software; you can redistribute it and/or
modify it under the terms of the GNU Lesser General Public
License as published by the Free Software Foundation; either
version 2.1 of the License, or (at your option) any later version.

IMU configuration : Vectornav Protocol
Baud rate         : 57600
VN-100 Sentences  : $VNYPR : Yaw, Roll, Pitch System Fix Data
		
	Methods:
		Init() : VN-100 Initialization
		Read() : Call this funcion as often as you want to ensure you read the incomming IMU data
	
	Send the request via the serial port to the VN-100(t), the parsing code will capture the 
	response and store it in one of the assiciated variables listed in the header file
	
	Variables:
		Yaw, Pitch, Roll		        - Yaw, Pitch and Roll
		Q[0,1,2,3]				- Quarternion measurements
		Magnetic[0,1,2]			        - Magnetic [X,Y,Z] measurements
		Acceleration[0,1,2]		      	- Acceleration [X,Y,Z] measurements
		Angular[0,1,2]			        - Acceleration [X,Y,Z] measurements
		DCM[0,1,2,3,4,5,6,7,8]	    		- Directional Cosine Orientation Matrix
                                  			=	|0  1  2|
								|3  4  5|
								|6  7  8|
					
