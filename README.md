# haproxy-loadbalancing-lab

HAProxy Load Balancing Lab

## Objective
Set up HAProxy as a load balancer for two web servers with different content. Implement and test different load balancing algorithms.

1. Deploy two web servers with **different** content
2. Install and configure HAProxy as load balancer on a different VM
3. Implement different algorithms:
    - Round-robin
    - Least connections
    - IP hash
4. Configure health checks
5. Test load distribution (you can use Apache Bench or any other testing tool)

**Deliverables:**

- Complete HAProxy configuration file
- Load balancing test results for each algorithm
- Screenshots of HAProxy statistics page
- Performance comparison report
- Health check logs


## Repository Structure

- **haproxy-loadbalancing-lab/**
  - [configs/](https://github.com/oydpete/haproxy-loadbalancing-lab/tree/main/configs)
    - [haproxy.cfg](https://github.com/oydpete/haproxy-loadbalancing-lab/blob/main/configs/haproxy.cfg)

  - documentation/
    - [implementation.md](https://github.com/oydpete/haproxy-loadbalancing-lab/blob/main/Documentation/Implementation.md)
    - [testing.md](https://github.com/oydpete/haproxy-loadbalancing-lab/blob/main/Documentation/Testing.md)
    - [screenshots/](https://github.com/oydpete/haproxy-loadbalancing-lab/tree/main/Documentation/Sreenshot)
      - haproxy_stats_round_robin.png
      - haproxy_stats_least_connections.png
      - haproxy_stats_ip_hash.png

  - README.md

## OBSERVATION & CONCLUSION
It was observed from the Load Distribution test that the IP Hash Algorithm, Least Connection Algorithm and Round-robin Algorithm had an average of

* 0.044s, 0.042s, 0.040 for time taken for tests respectively

* 2271.49, 2405.64 , 2509.78 request per second respectively
  
* 4.402ms, 4.157ms, 3.986 Time per request(maean) respectively
  
* 592.27kb/s, 627.25kb/s , 654.14 and Transfer rate respectively


## CONCLUSION
From the tests , it is can be concluded that the Round-robin Alogrothm is the faster and more effient load balancing technique followed by the Least connection Algotrithm


  
