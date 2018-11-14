# Server Load Balancer FAQ {#concept_a4t_1h5_vdb .concept}

## 1. What scheduling algorithms are supported by Server Load Balancer \(SLB\)? {#section_hy3_g35_vdb .section}

The following scheduling algorithms are supported:

-   Round robin \(RR\): Requests are distributed across the group of backend ECS servers sequentially.
-   Weighted round robin \(WRR\): You can set a weight for each backend server. Servers with higher weights receive more requests than those with lower weights.
-   Weighted least connections \(WLC\): In addition to the weight set to each backend ECS server, the number of connections to the client is also considered. A server with a higher weight value will receive a larger percentage of live connections at any one time. If the weights are the same, the system directs network connections to the server with the least number of established connections.

## 2. What is the difference between an Internet Server Load Balancer and an intranet Server Load Balancer? {#section_kcm_335_vdb .section}

-   The Internet SLB can distribute client requests from the Internet. A public IP is assigned to an Internet SLB instance.
-   The intranet SLB can only distribute client requests from the intranet. A private IP is assigned to an intranet SLB instance.

## 3. Can I modify the Server Load Balancer instance type? {#section_l11_k35_vdb .section}

No.

The SLB system allocates an instance IP \(a public IP or a private IP\) based on the SLB instance type. To switch the SLB instance type, you must first delete the instance and create a new SLB instance of the expected type.

## 4. Is the allocated IP address exclusive to the SLB Instance? {#section_jkl_m35_vdb .section}

Yes. The IP address of the SLB instance is exclusive to the load balancing service you purchased during the entire lifecycle. Changing the SLB configurations and listening rules will not affect the IP address.

If the SLB IP has been resolved to a domain name to provide Internet services, do not delete the corresponding SLB instance unless necessary. The configurations and the IP will be deleted along with the deletion of the instance and cannot be restored. If you recreate an SLB instance, the system will allocate a new IP.

## 5. Does SLB support HTTP redirection? {#section_qz5_435_vdb .section}

Yes.

SLB supports redirecting HTTP to HTTPS. For more information, see [Redirect HTTP to HTTPS](../../../../reseller.en-US/Archives/User Guide (Old Console)/Listener/Layer-7 listeners/Redirect HTTP to HTTPS.md#).

## 6. What is the difference between pinging the IP of the SLB instance and pinging the IP of a backend ECS instance? {#section_qvm_s3x_wdb .section}

When pinging the IP of an SLB instance, the response is sent from the SLB cluster. The request will not be forwarded to backend ECS instances. When pinging the IP of a backend ECS instance, the response is sent from the backend ECS instance and has no relationship with the SLB.

## 7. Does SLB rely on the Internet bandwidth? {#section_ywk_v3x_wdb .section}

The communication between the SLB and backend ECS instances goes through the intranet, therefore, no need to configure extra Internet bandwidth for backend ECS instances.

However, if you want to provide Internet services through both the SLB and ECS instances at the same time, the corresponding ECS instances need to be configured with sufficient Internet bandwidth. The Internet bandwidth of backend ECS instances has no impact on the service capability of the SLB.

## 8. Is there any impact on the load balancing service if the Internet NIC is disabled? {#section_wmt_w3x_wdb .section}

If the ECS instance has configured a public IP, disabling the Internet NIC will impact the load balancing service.

The traffic goes through the Internet NIC If the backend ECS is configured with a public IP. When the Internet NIC is disabled, the returned data packet cannot be sent. We recommend you do not disable the Internet NIC. But if you have to, you can modify the default route to intranet to avoid the impact on the service. However, you need to consider whether the business is Internet-dependent, such as accessing RDS through the Internet.

## 9. How to avoid the service failure of the SLB itself? {#section_ihr_y3x_wdb .section}

-   Add ECS instances of different zones as backend servers for the Server Load Balancer instance to improve local availability.
-   Create multiple SLB instances in the same region and use DNS to provide Internet services to improve the local availability.
-   Create multiple SLB instances in different regions and use DNS to provide Internet services to improve the cross-region availability.

## 10. What does the SLB balance? {#section_tbb_bjx_wdb .section}

The SLB distributes network traffic to backend ECS instances according to the specified scheduling algorithm:

-   Layer-4 listeners distribute the traffic based on TCP connections. If you create a socket through TCP or UDP to access the Server Load Balancer instance, the source and destination IPs and the ports form a connection.
-   Layer-7 listeners distribute the traffic based on HTTP requests, such as an HTTP GET request.

## 11. Why is the traffic not balanced? {#section_wxp_cjx_wdb .section}

The following are possible reasons:

-   Have enabled session persistence

    If session persistence is enabled, it will cause traffic imbalance when fewer clients are accessing the SLB instance. This is especially common when a small number of clients are used to test the SLB instance. For example, session persistence \(source-IP-based\) is enabled for a TCP listener and a client is used to test the load balancing service.

-   Abnormal ECS status

    Backend servers with abnormal heath status can also lead to an imbalance especially during stress test. If the health check for a backend ECS instance fails or its health status changes frequently, this will cause an imbalance.

-   TCP Keepalive

    When some backend ECS instances enable TCP Keepalive and others do not, the connections will accumulate on the ECS instances with TCP Keepalive enabled. This scenario will cause an imbalance.

-   Troubleshoot
    -   Check whether the weights of backend ECS instances are the same;
    -   Check if the health check of the backend ECS instances fails or if the health status is unstable in a specified period. Check if the health check is correctly configured with the status code.
    -   Check if both the WLC scheduling algorithm and session persistence are enabled. If so, change the scheduling algorithm to WRR and session persistence.

## 12. Why each connection does not reach the bandwidth peak? {#section_ggl_fjx_wdb .section}

Because the SLB is deployed in cluster to provide the load balancing service, all requests are distributed evenly on the SLB system servers. Similarly, the specified bandwidth is also evenly distributed to these servers.

The calculation method of the traffic ceiling for a single connection download is: Single connection download peak = The configured total bandwidth of Server Load Balancer / \(N-1\). N represents the number of traffic forwarding groups, and the current value is 4. For example, if you have set the bandwidth ceiling to 10 MB in the console, the maximum traffic for downloading of each client is 10/\(4-1\), or 3.33 MB.

Considering the implementation principles of Server Load Balancer, we recommend you set a reasonable bandwidth peak value for a single listener based on your business conditions and implementation modes to eliminate negative impact and limitations on your external services.

## 13. Why does the SLB compression fail? {#section_kt2_hjx_wdb .section}

View the file's content-type attribute. If the file type is not text/xml, text/plain, text/css, application/javascript, application/x-javascript, application/rss + xml, application/atom + xml or application/xml, the compression fails.

Resolution:

-   Modify the file's content-type attribute at the source site to change the file type to a type supported by the Server Load Balancer.
-   Modify the Layer-7 SLB instance listener to a Layer-4 SLB instance listener.

## 14. How to query the load balancing traffic usage? {#section_v2h_kjx_wdb .section}

Consumption details

Log on to the billing management console, in the Billing Management navigation pane, click **Resource Packages** \> **Usage Records**. Select **Server Load Balancer \(SLB\)** to view the consumption details of SLB.

Traffic usage

On the SLB details page, click **Monitoring** to view traffic usage.

The monitoring data may be different from the traffic data in the consumption details. For more information, see [Monitoring data and billing data](../../../../reseller.en-US/Pricing/Monitoring data and billing data.md#).

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/4286/15421822683190_en-US.png)

## 15. Why cannot I modify the bandwidth by calling the API? {#section_ldl_zkx_wdb .section}

If the following error occurs when calling the API to modify the bandwidth, it indicates that the peak bandwidth set on the console conflicts with the value set in the API. Error message: `Code":"InvalidParameter","Message":"The specified parameter bandwidth is not valid."`. You have to change the peak bandwidth on the console.

## 16. Why is the monitoring data different from the actual billing data? {#section_is3_hlx_wdb .section}

-   Monitoring data is collected every one minute by the Server Load Balancer system, and reported to the cloud monitoring system. Then, the cloud monitoring system calculates the average value of all collected data in each 15 minutes. Billing data is collected at the same granularity and the Server Load Balancer system reports the accumulated value in each hour to the billing system.

    The monitoring data is the calculated average value, but the billing data is the accumulation value. These two data sets are incomparable because they are calculated and generated differently.

-   Server Load Balancer provides real-time monitoring data. However, a short delay may inevitably occur in the data collection, calculation, and display process. Although this delay is almost insignificant, it can create a certain degree of discrepancy between the monitoring and billing data. Billing data tolerates a maximum delay of three hours. For example, billing data generated between 01:00-02:00 is normally reported to the billing system at 03:00, but is allowed to be reported to the billing system at 05:00. As a result, there are differences between billing data and monitoring data.
-   The product definitions of monitoring and billing data are also different. The purpose of monitoring is to help users observe if the instance is in abnormal conditions. If so, users can resolve the problem as soon as possible. The purpose of billing is to generate bills. Monitoring data cannot be used as the billing data.

## 17. What are the timeout values of each listener? {#section_aw5_jlx_wdb .section}

-   TCP listener: 900 seconds
-   UDP listening: 90 seconds
-   HTTP listener: 60 seconds
-   HTTPS listener: 60 seconds

## 18. Why does the SLB connection time out? {#section_hkn_mlx_wdb .section}

From the server side, the following situations may cause the connection timeout:

-   The IP of the SLB instance is protected

    Such as the blackholing and scrubbing, as well as WAF protection.

-   Insufficient client ports

    Lack of client ports may lead to connection failure especially in the stress test. The SLB erases the timestamp attribute of the TCP connection. Therefore, the tw\_reuse parameter does not work and the time\_wait state connection heap causes the lack of the client ports.

    Resolution: Do not enable TCP Keepalive for the clients and use the RST packet instead of FIN packet to terminate the connection.

-   The accept queue of the backend server is full

    If the accept queue of the backend server is full, the backend server cannot sent the SYN\_ACK packet. Therefore, the connection times out.

    Resolution: The default value of net.core.somaxconn is 128. Run the `sysctl -w net.core.somaxconn=1024` command to change its value and restart applications on the backend servers.

-   Access the Layer-4 load balancing service from the backend servers

    For the Layer-4 load balancing service, the connection fails if you access the service from a backend server.

-   Improper RST configuration

    If no data is transferred within 900 seconds after the TCP connection is established on the SLB, the system will send the RST packet to the client and the backend server to terminate the connection. If the RST configuration is not correct on the backend server, the backend server may send data to a closed connection, which leads to connection timeout.


