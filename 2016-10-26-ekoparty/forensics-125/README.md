#Knock Knock (for, 125 points, solved by 9)
###What are they talking about?

___________________________________________________________

1. Extract an archive. View file "nanunanu". 

```
;Rate: 1000000
;Channels: 5
0000000a@0
00000008@5
0000000a@17
00000008@23
0000000a@29
00000008@35
0000000a@41
00000009@48
0000000b@54
..........
```

2. We can see a dump. Let's go deeper. First, we can see that every moment we send/receive 1-byte. Using this we can propose possible protocols: it could be RS-232 (UART), USB, 1-Wire, CAN, I2C. 

3. Open this file in protocol analyser. I've used [Logic Sniffer](https://www.lxtreme.nl/ols/#download)

4. Possibly it can be [I2C](https://en.wikipedia.org/wiki/I%C2%B2C).

5. I2C interface uses 2 bus: SDA and SCL. If you watch more properly, you can see that Channel 1 is SCL and Channel 0 is SDA.

6. Decode a message from ASCII. Get the flag: 

```
EKO{oh..icu2}
```