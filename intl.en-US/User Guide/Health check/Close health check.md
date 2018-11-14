# Close health check {#task_it1_1qn_vdb .task}

If health check is closed, requests may be distributed to unhealthy ECS instances, which can lead to service interruption. In general, we do not recommend closing health check.

**Note:** You can only close health check for HTTP and HTTPS listeners. The health check of UDP and TCP listeners cannot be closed.

1.  Log on to the [SLB console](https://partners-intl.aliyun.com/login-required#/slb). 
2.  On the Instances page, click the ID of the target instance. 
3.  In the Listeners tab, click **Configure** in the **Actions** column of the target listener. 
4.  On the Configure Listener page, click **Next** until the **Health Check** tab is displayed. 
5.  Close the health check switch, click **Next**, click **Submit**, and then click **OK**. 

