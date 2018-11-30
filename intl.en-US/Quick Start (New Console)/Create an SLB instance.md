# Create an SLB instance {#task_bh5_dll_vdb .task}

Before using Server Load Balancer, you must create a Server Load Balancer instance. You can add multiple listeners and backend servers to a Server Load Balancer instance. This tutorial provides step-by-step guidance on how to create an Internet SLB instance. After an Internet SLB instance is created, a public IP is allocated to it. You can resolve a domain to this IP.

1.   Log on to the [SLB](https://partners-intl.console.aliyun.com/#/slb) console. 
2.  On the Server Load Balancer page, click **Create Server Load Balancer**. 
3.  Configure the instance according to [Create an SLB instance](../../../../reseller.en-US/User Guide/Server Load Balancer instance/Create an SLB instance.md#). The configurations for the Server Load Balancer instance in this tutorial are as follows:
    -   **Region**: Server Load Balancer does not support cross-region deployment. The region must be the same for the Server Load Balancer instance and ECS instances. In this tutorial, select **China \(Hangzhou\)**.
    -   **Zone Type**: Multiple zones have been deployed in most regions for better disaster tolerance. Server Load Balancer can switch to the backup zone to provide the load balancing service when the primary zone is unavailable, and will automatically switch back to the primary zone when the primary zone is recovered.

        In this tutorial, select **China East 1 Zone B** as the primary zone and **China East 1 Zone D** as the backup zone.

    -   **Instance Type**: Select **Internet**.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15700/15435710227476_en-US.png)

4.   Click **Buy Now** and complete the payment. 
5.   Go back to the SLB console. 
6.   On the Server Load Balancer page, select the **China \(Hangzhou\)** region. Hover the mouse pointer to the instance name area and then click the pencil icon. Enter **SLB1** as the name of the instance, click **OK**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15700/15435710227482_en-US.png)


[Resolve a domain name](reseller.en-US/Quick Start (New Console)/Resolve a domain name.md#)

