# Network traffic flow {#concept_ev3_wsm_vdb .concept}

As a traffic forwarding service, SLB forwards requests from clients to backend servers through the SLB cluster and then the backend servers return the responses to SLB through the intranet.

## Inbound network traffic {#section_fxh_xgn_vdb .section}

SLB distributes incoming traffic according to forwarding rules configured on the console or API. The inbound network traffic flow is shown as [Figure 1](#fig_og4_jfp_h2b).

![](../DNSLB11827830/images/2333_en-US.png "Inbound network traffic")

1.  For TCP/UDP protocol and HTTP/HTTPS protocol, the incoming traffic must be forwarded through the LVS cluster first.
2.  Numerous inbound traffic is distributed evenly among all node servers in the LVS cluster, and the node servers synchronizes session to guarantee high availability.
    -   For Layer-4 listeners \(the frontend protocol is UDP or TCP\), the node servers in the LVS cluster distribute requests directly to backend ECS instances according to the configured forwarding rules.
    -   For Layer-7 listeners \(the frontend protocol is HTTP\), the node servers in the LVS cluster first distribute requests to the Tengine cluster. Then, the node servers in the Tengine cluster distribute the requests to backend ECS instances according to the configured forwarding rules.
    -   For Layer-7 listeners \(the frontend protocol is HTTPS\), the request distribution is similar to the HTTP protocol. However, before distributing the requests to backend ECS instances, the system will call the Key Server to validate certificates and decrypt data packets.

## Outbound network traffic {#section_jcv_ghn_vdb .section}

SLB communicates with backend ECS instances through the intranet.

-   If the backend ECS instances only need to handle the traffic distributed from SLB, no public bandwidth \(EIP, NAT Gateway and public IP\) is required.
-   However, if you want to provide external services from a backend ECS instance, or the backend ECS instance needs to access the Internet, you must configure a public IP, an EIP or a NAT Gateway.

The outbound network traffic flow is shown as [Figure 2](#fig_s3w_zmt_h2b).

![](../DNSLB11827830/images/2335_en-US.png "Outbound network traffic")

In general, the traffic goes out from where it comes in:

1.  For the traffic coming from SLB, billing and speed limitation are done on SLB. You are charged by the outbound traffic and not the inbound traffic \(the rule may change in the future\). SLB communicates with the backend ECS instances through the intranet and no traffic fee is charged for the internal communication.
2.  For the traffic coming from the EIP or NAT Gateway, billing and speed limitation are done on EIP or NAT Gateway. If the ECS instance has configured a public IP when it is created, the billing and speed limitation are done on the ECS instance.
3.  SLB only provides the function of being accessed from the Internet. That is, a backend ECS instance can only access the Internet when it responds to the request forwarded by SLB. If you want to actively access the Internet from a backend ECS instance, you must configure a public IP \(configure EIP or NAT gateway\) for the ECS instance.
4.  A public IP \(configured when you create an ECS instance\), EIP, and NAT gateway can all achieve mutual Internet access \(access or accessed\), but they cannot forward traffic or balance traffic loads.

