# Task: Load Balancer Implementation
**Objective:** Set up HAProxy as a load balancer for web servers

## **TASK :**
Test different algorithms for Round-robin, Least connections, IP hash:

1. Configure health checks

2. Test load distribution (you can use Apache Bench or any other testing tool)




*****

### STEP 1 : Configure for health check & Install Apache Bench 

* Through sudo nano configure for health check

        listen stats
            bind *:8080  
            stats enable  
            stats uri /stats  
            stats refresh 5s  
            stats auth admin:password  # Change 'admin' and "password as     needed


* Install Apache Bench 

        sudo apt install -y apache2-utils 

![alt text](<../../../Desktop/NexaCloud/Machine/install tester.png>)


*******


## **TESTS & RESULTS**

*******



## **Round-robin Algorithm**

***********************



### Health Check Stat

* In Browser, 

        http://192.168.56.14:8080/stats

* **Result:**

   ![alt text](<Documentation/first stat.png>)



### Load Distribution Test

* Input this code into powershell

        ab -n 100 -c 10 http://192.168.56.14/

* **Result1:**

   ![alt text](<../../../Desktop/NexaCloud/Machine/health check final.png>)


### Health Check Logs

* Input this into powershell

        sudo tail -f /var/log/haproxy.log



* **Result:**

![alt text](<../../../Desktop/NexaCloud/Machine/health check.png>)



*************************************************


***********************************************





## Least connections Algorithm


### Health Check Stat

* In Browser, 

        http://192.168.56.14:8080/stats


* **Result:**

  ![alt text](<../../../Desktop/NexaCloud/Machine/least conn state.png>)


### **Load Distribution Test**

 * Input this code into powershell

        ab -n 100 -c 10 http://192.168.56.14/


* **Result:**

  ![alt text](<../../../Desktop/NexaCloud/Machine/least connnect out1.png>)

### Health check logs

* Input this into powershell

        sudo tail -f /var/log/haproxy.log


* **Result:**

  ![alt text](<../../../Desktop/NexaCloud/Machine/least conn log 2.png>)


# IP hash Algorithm

*******

### Health Check Stat

* In Browser, 

        http://192.168.56.14:8080/stats


* **Result:**

![alt text](<../../../Desktop/NexaCloud/Machine/hash stATE.png>)



### **Load Distribution Test**


* Input this code into powershell

        ab -n 100 -c 10 http://192.168.56.14/


* **Result:**

  ![alt text](<../../../Desktop/NexaCloud/Machine/hash output 1.png>)


### Health check logs

* Input this into powershell

        sudo tail -f /var/log/haproxy.log


* **Result:**

  ![alt text](<../../../Desktop/NexaCloud/Machine/hash log.png>)



## OBSERVATION & CONCLUSION

It was observed from the Load Distribution test that the IP Hash Algorithm, Least Connection Algorithm  and Round-robin Algorithm  had an average of 

* 0.044s, 0.042s, 0.040  for time taken for tests respectively
* 2271.49, 2405.64 , 2509.78 request per second respectively
* 4.402ms, 4.157ms, 3.986 Time per request(maean)  respectively
* 592.27kb/s, 627.25kb/s , 654.14 and Transfer rate respectively 

### CONCLUSION

From the tests , it is can be concluded that the Round-robin Alogrothm is the faster and more effient load balancing technique followed by the Least connection Algotrithm
