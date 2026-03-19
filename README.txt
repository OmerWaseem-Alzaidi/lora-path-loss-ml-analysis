README FILE

DESCRIPTION
The dataset contains the path loss measurements collected to test the four localization algorithms as described in sec. VII.
The dataset can be used to test RSS-based localization algorithms with experimental data of a radio network covering both outdoor and indoor areas.

SIZE
The dataset has a total size of 80 kB aside from the README, which has the size 4 kB.

PLATFORM AND ENVIRONMENT
Many common platforms and environments can work with the dataset, for example, Windows 10 and MATLAB R2019b (some hardware details in Table V). 

MAJOR COMPONENT DESCRIPTION
Each .txt file specifies in the first line the receiver which collected the data contained in the file. Accordingly, the file "Anchor 1" contains the measurements collected by receiver 1 in Fig. 8, "Anchor 2" by receiver 2, and so on.
The receivers move as detailed in Fig. 8, and the raw data collected in the .txt were averaged on three packets to improve the accuracy of the path loss measure.
The measurement points set along the receivers paths are (in m; vector=[StartPoint:Step:EndPoint EventualAdditionalPoint]; axes w.r.t. Fig. 8):
-anchor 1, x=[2.5:1.5:59.5 62], y is fixed to 58;
-anchor 2, x is fixed to 62, y=[57:-1:18];
-anchor 3, x=[59.5:-1.5:1], y is fixed to 18;
-anchor 4, x is fixed to 1, y=[19:1:58];
-anchor 5, x=[2.5:1.5:59.5 62], y is fixed to 9. 
In every measurement point, the path loss measurement is obtained averaging over the three packets here collected. For example, in the point (2.5, 58), the measurement is given by averaging the first 3 packets of anchor 1, in (4,58) packets from 4 to 6 of anchor 1, and so on.
Each "Anchor [number]" has the following columns:
-timestamp: timestamp of the received packet according to the inner clock of the receiving board (last figure in microseconds);
-rssi: this column contains the received signal strength indicator normalized by the receiving and transmitting gains and the transmitting power. The values are rounded to the nearest integer. It is in the dB scale. 
-snr: this column contains the signal-to-noise ratio in dB scale;
-sfrx: this column contains the spreading factor of the LoRa protocol employed, as to say 7;
-tx_power: this column is set to 14, as to say the transmitting power in dBm scale.
The others columns' values are set to zero.
Transmitter true position: [44 0]

DETAILED INSTRUCTIONS
According to (3), the PL value of the received packet is given by:
-rssi_n+10*log10(1+1/(10^(SNR/10))),
where rssi_n is the normalized rssi (i.e., the values in the rssi column of the "Anchor [x]" files) and SNR is the value in the snr column of the .txt file.
Please note that the measurements are affected by a high additional noise as detailed in sec. III and VII.
After evaluating the PL of all the packets, the PL has to be averaged on the three consecutive packets collected in the same measurement point to obtain an accurate PL value.
Accordingly, the first input subset of Fig. 9 is given by the 5 PL measurements (one per receiver) averaged on the first 3 packets. The second input subset is composed of 10 measurements (first subset and subsequent 5 PL measurements) and so on. 

OUTPUT DESCRIPTION
The data used as temporally ordered input to the four algorithms in sec. VII return as output the plot in Fig. 9.

CONTACT INFORMATION
For any issue or further information regarding the dataset, please write an email to the contact author at the following address:
giulio.maria.bianco@uniroma2.it	