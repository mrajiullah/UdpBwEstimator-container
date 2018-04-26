SRC1=udp_bw_est_srvr.c
SRC2=udp_bw_est_rcvr.c
HDRS=udp_bw_est_packets.h 
CPLR=gcc
BNAME_S=UDPbwEstimatorSrv 
BNAME_R=UDPbwEstimatorRcvr

all: BNAME_S BNAME_R

BNAME_S: $(SRC1) Makefile
	$(CPLR) $(SRC1) -lm -lpthread -o $(BNAME_S)
BNAME_R: $(SRC2) Makefile
	$(CPLR) $(SRC2)  -o $(BNAME_R)
clean:
	rm -rf $(BNAME_S) $(BNAME_R)
