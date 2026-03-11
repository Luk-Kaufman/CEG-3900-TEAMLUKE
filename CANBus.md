## CAN Bus
- A standard that allows devices to communicate with each other > used in cars,  tires > speedometer, tire pressure > pressure alert
Able to view in Wireshark, but you can’t just look at Wireshark
   - Using the can.id filter, to specifically look for one type of message
Looking over the code 
   - This code snippet gives us the overall speed of the vehicle
```
int speed_id = 589;
int speed_pos = 3;
struct canfd_frame frame;

while (PollEvent(&event) != 0) {
    read_data(&event, &frame);
    if (frame.can_id == speed_id) {
        double speed = frame->data[speed_pos] << 8;
        speed += frame->data[speed_pos + 1];
        speed = speed / 100;
        speed = speed * 0.6213751;
        update_speed(speed);
    }
}
```
      - int speed_id = 589; > Checks for the CAN Bus id of 589
      - int speed_pos = 3; > 3rd byte

- In Wireshark, then Excel:
1. Open `candump.pcap` in Wireshark  
2. Right-click `ID → Apply as Column.`
3. Right-click `Data → Apply as Column.`
4. Export the file as a CSV
5. Analyze in Excel > Remove duplicates
6. Finally convert from kph to mph, `speed = speed * 0.6213751`
7. Final answer
- 1. 36

1. In excel find the ID 589 > this is the speed
- 2. 352

1. Since our speed position was 3, we will look at the 3rd byte > In this case, the 3rd byte is 0c
2. So on the script `double speed = frame->data[speed_pos] << 8;`, replace with `speed = 0x0c << 8` > Hexadecimal.
3. Next, we have `speed += frame->data[speed_pos + 1];`, Since we add one to the position we are at 4 and 4 is a8, so `speed += 0xa8`
4. Next we divide the speed by 100
- 3. 20.133
