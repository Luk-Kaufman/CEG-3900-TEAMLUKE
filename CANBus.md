## CAN Bus
- A standard that allows devices to communicate with each other > used in cars,  tires > speedometer, tire pressure > pressure alert
Able to view in Wireshark, but you can’t just look at Wireshark
   - Using the can.id filter, to specifically look for one type of message
Looking over the code 
   - This code snippet gives us the overall speed of the vehicle

      - int speed_id = 589; > Checks for the CAN Bus id of 589
      - int speed_pos = 3; > 
