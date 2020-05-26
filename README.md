                                            # Adjust Technical Test #


Description: I have used this repository to submit both questions. 


Question 1. Please write a simple CLI application in the language of your choice that does the following 
Print the numbers from 1 to 10 in random order to the terminal.

Solution: I have written a shell script file that you need to run with the below command on your terminal this script will run on Mac and Linux both machine. 



# Step to run the shell script #

####### Run the following command step by step to Clone the GitHub Repository and execute shell script ####

$git clone https://github.com/Mdaftab/Adjust-test.git
$cd Adjust-test/
$chmod +x testscript.sh
$. testscript.sh 

when you run the script it will give you the random number from 1-10. 



Question 2. Imagine a server with the following specs:

- 4 times Intel(R) Xeon(R) CPU E7-4830 v4 @ 2.00GHz

- 64GB of ram

- 2 tb HDD disk space

- 2 x 10Gbit/s nics

The server is used for SSL offloading and proxies around 25000 requests per second.
Please let us know which metrics are interesting to monitor in that specific case and how would you do that? What are the challenges of monitoring this?


Solution:

Why we do SSL Offloading: 
The web request is sent by the User (Browser) via SSL protocol to the Load Balancer or SSL Offloader server, the connection created between User and SSL Offloader is in encrypted form. SSL Offloader takes care of encryption and decryption of data and sends plain requests to Web Servers attached behind in the same private network. Offloading or moving the burden from the web server’s and takes care of all encryption and decryption, this can largely boost up the performance of the webserver, a high number of requests can be processed concurrently with very low CPU usage.



There are 3 main components I would like to monitor in this particular case along with the system basic health Matrix (Memory, Total CPU, Storage )


1. Transactions Per Second 
2. Bulk Throughput
3. Concurrent Connection


Transactions Per second :
Memory allocation for a Service Engine, which primarily impacts the number of concurrent connections, can be anywhere between 1 and 128 GB. As a general rule of thumb, SSL connections consume about twice as much memory as HTTP layer 7 connections, and four times as much memory as layer 4 with TCP proxy.

Bulk Throughput:
The maximum throughput for an SSL terminated virtual service depends on CPU as well as the NIC. 
Using multiple NICs for client and server traffic can reduce the possibility of congestion or NIC saturation.  The maximum packets per second for virtualized environments vary dramatically and will be the same limit regardless if the traffic is SSL or unencrypted HTTP.  For best throughput, I would recommend bare metal or Linux cloud servers with Intel NICs capable of DPDK.


Concurrent Connection:
Often overlooked when capacity planning for SSL is the impact on concurrent connections. Often administrators hear numbers of tens of millions of concurrent numbers achieved by a load balancer, so no further attention is paid to this metric. The concurrent benchmark numbers floating around are generally for layer 4 in a pass-through, or non-proxy mode. In other words, they are many orders of magnitude greater than what will be achieved. As a rough yet conservative estimate, assume 40kB of memory per SSL terminated connection in the real world. The amount of HTTP header buffering, caching, compression, and other features play a role in the final number. including methods for optimizing for greater concurrency.



Monitoring:

As per the current industry Datadog and Newrelic are the best APM, thread monitoring tools in the market. I have worked on both of them and would like to suggest to the company. 
