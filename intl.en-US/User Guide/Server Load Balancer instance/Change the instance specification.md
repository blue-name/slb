# Change the instance specification {#task_epd_ctm_vdb .task}

You can change a shared-performance instance to a guaranteed-performance instance, or change the specification of a guaranteed-performance instance.

Before modifying the instance configuration, note the following:

-   If you change a shared-performance instance to a guaranteed-performance instance, a brief disconnection of service may occur for 10 to 30 seconds.

    We recommend that you change the configuration in the low traffic period, or use DNS to schedule services to other SLB instances first before changing the configuration.

-   After you change a shared-performance instance to a guaranteed-performance instance, you cannot change it back.

    You can use the \(slb.s1.small\) specification after changing the instance to a guaranteed-performance instance.


1.   Log on to the [SLB console](https://partners-intl.aliyun.com/login-required#/slb). 
2.   Select a region. 
3.  Find the target instance, select **More** \> **Change Specification**. 
4.  In the Configuration Upgrade area, select a new specification, and complete the payment. 

