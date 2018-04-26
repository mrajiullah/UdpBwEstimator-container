# UDPbwEstimator
A Linux based lightweight tool to estimate available down-link bandwidth. UDPbwEstimator consists of a server that sends n number of back to back UDP packets in the beginning of each second. The receiver tells the server about the number of packets, bursts to be sent. Then receiver 
calculates the bandwidth using packet arrival times and payloads. 

By providing the receiver with a file name, the arrival time of each packet is
written to a file. This can be processed using the included python-script
(parse\_recv\_times.py), which accepts number of back to back packets, the log file name and number of bursts as input parameters. It then shows the down-link bandwidth calculated for each burst. 

A Makefile is provided in order to compile the application. There are no external dependencies.

The receiver accepts the following command line options:

* -c : Number of back to back packets (required).
* -b :  number of bust to be sent (required).
* -l : Payload length in bytes.
* -s : Source IP to bind to (required).
* -d : IP of traffic generator (required).
* -p : Port at traffic generator (required).
* -w : Filename for writing packet timestamps (optional).

The server accepts the following command line options:

* -s : Source IP to bind to (required).
* -p : Source port (required).

Further, the generator creates a thread pool and serves one receiver
per thread. If you want to change the number of threads, change the value of
NUM\_THREADS at the top of udp\_bw\_est\_srvr.c
