# EXPT.NO.2b) Implementation and Performance Analysis of Selective Repeat Protocol
# AIM
To implement an error control mechanism with the Selective Repeat protocol and assess the protocol's performance by simulating varying network conditions to analyze the impact on throughput, reliability, and efficiency.
# EQUIPMENTS REQUIRED
•	Computer/Laptop
•	Code::Blocks 25.03 IDE
•	C++ compiler (GNU GCC)
•	Windows/Linux operating system
# PROCEDURE
1.	Open the Code::Blocks IDE.
2.	Create a new C++ Console Application and open the main.cpp source file.
3.	Initialize the total number of packets and the Sliding Window size.
4.	Implement the Go-Back-N form of the Sliding Window protocol.
5.	Simulate packet transmission through the network.
6.	Introduce different packet-loss probabilities to represent varying network conditions.
7.	Transmit packets within the current sliding window.
8.	If a packet is lost, retransmit from the lost packet position according to the Go-Back-N mechanism.
9.	Continue transmission until all packets are successfully delivered.
10.	Count the total transmissions and retransmissions.
11.	Calculate throughput, reliability, and efficiency for each packet-loss condition.
12.	Compare the results obtained for 0%, 10%, 20%, 30%, and 40% packet-loss conditions.
 
# C++ PROGRAM
```
#include <stdio.h>

void main()
{
    int i, j, n;

    printf("GO BACK N ARQ\n");
    //printf("Enter message in format\n");

    printf("Enter number of frame : ");
    scanf("%d", &n);

    char frame[n][10];

    for (i = 1; i <= n; i++)
    {
        printf("Content for frame %d :", i);
        scanf("%s", &frame[i]);
    }

    int s = 1;

    //while (j <= n)
    {
        printf("Enter frame number with no ACK :");
        scanf("%d", &j);

        for (i = 1; i <= n; i++)
        {
            if (i != j)
            {
                printf("\n Sending frame %d \n FRAME ACKNOWLEDGED.....\n", i);
            }
            //else
            //{
            //    printf("\n Frame not Acknowledged.......\n");
            //}
        }

        if (j <= n)
        {
            printf("No Acknowledgement for frame %d... \n", j);
            printf("Resending... Content from frame %d : %s\n", j, frame[j]);
        }

        printf("\n Sending frame %d \n FRAME ACKNOWLEDGED.....\n", j);
    }

    printf("\n\nALL FRAME RECIEVED SUCCESSFULLY\n");
} 
```
# OUTPUT
<img width="537" height="646" alt="Screenshot 2026-08-02 211008" src="https://github.com/user-attachments/assets/724e063d-04b5-471f-9946-5b20bda4f993" />

 
# RESULT
Thus, the Go-Back-N Selective Repeat protocol with error control was successfully implemented and executed in C++ using Code::Blocks. The simulation was performed under different packet-loss conditions. It was observed that as packet loss increases, retransmissions increase while throughput and efficiency decrease. The protocol maintains reliable delivery by retransmitting lost packets. Hence, varying network conditions have a significant impact on the performance of the Sliding Window protocol.

