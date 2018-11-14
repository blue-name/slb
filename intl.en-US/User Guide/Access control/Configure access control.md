# Configure access control {#concept_f1l_pzb_wdb .concept}

Server Load Balancer allows you to configure access control for listeners. You can configure different whitelists or blacklists for different listeners.

You can configure access control when you create a listener or change access control configuration after a listener is created.

This document introduces how to configure access control after a listener is created.

## Enable access control {#section_ync_c1c_wdb .section}

Before enabling access control, make sure:

-   You have created an access control list. For more information, see [Configure an access control list](reseller.en-US/Archives/User Guide (Old Console)/Access control/Configure an access control list.md#).
-   You have created a listener.

To enable access control, complete these steps:

1.  Log on to the [SLB console](https://partners-intl.aliyun.com/login-required#/slb).
2.  Select a region.
3.  Click the ID of the target SLB instance.
4.  On the Instance Details page, click the **Listeners** tab.
5.  Find the target listener, and then click **More** \> **Set Access Control**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15686/15421814497481_en-US.png)

6.  On the Access Control Settings page, enable access control, select the access control method and access control list, and click **OK**.
    -   **Whitelist**: Only requests from IP addresses or CIDR blocks in the selected access control lists are forwarded. It applies to scenarios where the application only allows access from some specific IP addresses.

        Enabling whitelist poses some business risks. After a whitelist is configured, only the IP addresses in the list can access the listener. If you enable the whitelist without adding any IP entry in the corresponding access control list, all requests are forwarded.

    -   **Blacklist**: Requests from IP addresses or CIDR blocks in the selected access control lists are not forwarded. It applies to scenarios where the application only denies access from some specific IP addresses.

        If you enable a blacklist without adding any IP entry in the corresponding access control list, all requests are forwarded.


## Disable access control {#section_amn_q1c_wdb .section}

To disable access control, complete these steps:

1.  Log on to the [SLB console](https://partners-intl.aliyun.com/login-required#/slb).
2.  Select a region.
3.  Click the ID of the target SLB instance.
4.  On the Instance Details page, click the **Listeners** tab.
5.  Find the target listener, and then click **More** \> **Set Access Control**.
6.  On the Access Control Settings page, disable access control and click **OK**.

