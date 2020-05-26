                                                # Adjust Technical Test #

         Descritpion: I have used this repository to submit both question. 
         
         
         Qestion 1. Please write a simple CLI application in the language of your choice that does the following 
         Print the numbers from 1 to 10 in random order to the terminal.
         
         Solution: I have write a shell script file that you need to run with the below command on your terminal this script will run on Mac and Linux both machine. 
         
                                             # Step to run the shell script #
          
          
          
          
            ####### Run the following command step by step to Clone the github Repository and execute shell script ####
            
         $git clone https://github.com/Mdaftab/Adjust-test.git
         $cd Adjust-test/
         $chmod +x testscript.sh
         $. testscript.sh 
         
         when you run the script it will give you the random number from 1-10. 
         
         
         
         Qestion 2. Imagine a server with the following specs:

              - 4 times Intel(R) Xeon(R) CPU E7-4830 v4 @ 2.00GHz

              - 64GB of ram

              - 2 tb HDD disk space

              - 2 x 10Gbit/s nics

The server is used for SSL offloading and proxies around 25000 requests per second.
Please let us know which metrics are interesting to monitor in that specific case and how would you do that?  What are the challenges of monitoring this?


         Solution:
         
         Why we do SSL Offloading
The web request is sent by the User (Browser) via SSL protocol to the Load Balancer or SSL Offloader server, the connection created between User and SSL Offloader is in encrypted form. SSL Offloader takes care of encryption and decryption of data and sends plain requests to Web Servers attached behind in the same private network. Offloading or moving the burden from the web server’s and takes care of all encryption and decryption, this can largely boost up the performance of the web server, a high number of requests can be processed concurrently with very low CPU usage.
         
         
         
