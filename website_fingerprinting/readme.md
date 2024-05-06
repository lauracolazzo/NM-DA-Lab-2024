# **Homework 2 - Website Fingerprinting**

## **Objective**
The homework required the implementation of a website fingerprinting approach able to classify the websites visited by a user by observing only the encrypted HTTPS traffic.

More in detail, it was asked to:
1.   **Create a dataset**: this should have been done by visiting 10 times 10
among the most popular news websites that do not require login. For each visit performed, packets exchanged between the requesting machine and the server should have been captured in a separate .pcap file

2.   **Extract Features**: 2 alternative methods were proposed to extract features from each capture collected:
    - (*Mandatory*) Extract biflow statistical feautures (both uplink and dowlink):
      - Number of packets up/down
      - Total bytes up/down
      - Min/max/mean/std of the packet size up/down
      - Min/max/mean/std IAT (Inter Arrival Time) up/down
    - (*Optional*) Extract the Cumulative Trace of packets exchanged, ignoring TCP ACKs, and sample its piecewise linear interpolant at 20 equidistant points. This method is based on an a approach proposed in the literature (Reference: *A. Panchenko et al. “Website Fingerprinting at Internet Scale NDSS 2016*)

3.   **Evaluate the performance of a K-NN approach**: the accuracy obtained by a K-NN classifier with values of K going from 1 to 10 should have been plotted on an Accuracy/K graph

The construction of the **training and test sets** for the predictive algorithm should have been performed in 2 different ways:
1.   At first, the data gathered on a particulare day should have been split in a training set (70%) and a test set (30%)

2.   Then, after some time (e.g. 1 day), an additional test set should have been built, by visiting the same 10 websites 3 times each. Subsequently, the performance obtained using the old training set and the newly created test set should have been compared with the approach using the old training and test sets.
