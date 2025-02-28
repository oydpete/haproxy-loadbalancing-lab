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
  - configs/
    - haproxy.cfg

  - documentation/
    - [implementation.md]
    - testing.md
    - screenshots/
      - haproxy_stats_round_robin.png
      - haproxy_stats_least_connections.png
      - haproxy_stats_ip_hash.png

  - README.md
  
