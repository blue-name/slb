# Anti-DDoS Basic {#concept_qtj_cqn_vdb .concept}

You can view Alibaba Cloud Security thresholds of an Internet SLB instance on the SLB console.

## Introduction to Anti-DDoS Basic {#section_cnq_p3c_wdb .section}

Alibaba Cloud provides up to 5 Gbps Anti-DDoS Basic for SLB. As shown in the following figure, all traffic from the Internet must first go through Alibaba Cloud Security before arriving at SLB. Anti-DDoS Basic scrubs and filters common DDoS attacks and protects your services against attacks such as SYN flood, UDP flood, ACK flood, ICMP flood, and DNS Query flood.

![](../DNSLB11827830/images/2870_en-US.jpeg)

Anti-DDoS Basic sets the scrubbing threshold and blackholing threshold according to the bandwidth of the Internet SLB instance. When the inbound traffic reaches the threshold, scrubbing or blackholing is triggered:

-   Scrubbing: When the attack traffic from the Internet exceeds the scrubbing threshold or matches certain attack traffic model, Alibaba Cloud Security starts scrubbing the attack traffic. The scrubbing includes packet filtration, traffic speed limitation, packet speed limitation and more.
-   Blackholing: When the attack traffic from the Internet exceeds the blackholing threshold, blackholing is triggered and all inbound traffic is dropped.

The thresholds are calculated based on the following principles:

-   The thresholds are determined by the bandwidth of the SLB instance, that is, the outbound bandwidth of the SLB instance. The thresholds are high when the bandwidth of the instance is high and vise versa.
-   The blackholing threshold is determined by the security credit score of the user.

    **Note:** The security credit score only influences the blackholing threshold and does not influence the scrubbing threshold.


Complete these steps to calculate the threshold:

1.  The SLB backstage provides the recommended threshold value that can ensure normal running of the instance according to the purchased bandwidth.

    **Note:** The outbound bandwidth of a Pay-As-You-Go instance is the peak bandwidth in the region. Currently the peak bandwidth in Mainland China is 5G. For more information, see [Peak bandwidths in different regions](reseller.en-US/Limits/Peak bandwidths in different regions.md#).

    -   The relationship between SLB bandwidth and traffic scrubbing threshold \(bits/s\)
        -   When the SLB bandwidth < 100 Mbps, the default traffic scrubbing threshold \(bits/s\) = 120 Mbps
        -   When the SLB bandwidth \> 100 Mbps, the default traffic scrubbing threshold \(bits/s\) = bandwidth\*1.2
    -   The relationship between SLB bandwidth and traffic scrubbing threshold \(packets/s\)

        Traffic scrubbing threshold \(packets/s\) = \(SLB bandwidth/500\) \* 150000

        The bandwidth is in Mbps.

    -   The relationship between SLB bandwidth and blackholing threshold \(bits/s\)
        -   When the SLB bandwidth < 1 Gbps, the default blackholing threshold \(bits/s\) = 2 Gbps
        -   When the SLB bandwidth\> 1 Gbps, the default blackholing threshold \(bits/s\) = MAX \(SLB bandwidth\*1.5, 2 G\)
2.  Alibaba Cloud Security calculates the threshold according to the recommended value, the security credit score and the resource conditions in different regions.
    -   Rules for determining the traffic scrubbing threshold \(bits/s\) and the traffic scrubbing threshold \(packets/s\)

        The minimum traffic scrubbing threshold \(bits/s\) is 1,000 M and the minimum traffic scrubbing threshold \(packets/s\) is 300,000.

        -   If the threshold recommended by SLB is lower than the minimum cleaning threshold, the minimum threshold is used.
        -   If the threshold recommended by SLB is higher than the minimum cleaning threshold, the recommended threshold is used.
    -   Alibaba Cloud Security determines the blackholing threshold according to the security credit score of the user.

## View thresholds {#section_f35_ljc_wdb .section}

You can view the thresholds of an instance on the SLB console as a RAM user. If not, you must authorize the RAM account first. For more information, see [Allow read-only access to Anti-DDoS Basic](#section_c4n_wjc_wdb).

To view thresholds, complete these steps:

1.  Log on to the [SLB console](https://partners-intl.aliyun.com/login-required#/slb).
2.  Select a region.
3.  Hover the mouse pointer to the DDoS icon next to the target instance to view the following thresholds. You can click the link to go to the DDoS console to view more information.
    -   Traffic Scrubbing Threshold \(bits/s\): When the inbound traffic exceeds this value, scrubbing is triggered.
    -   Traffic Scrubbing Threshold \(packets/s\): When the inbound packets exceed this value, scrubbing is triggered.
    -   Blackholing Threshold: When the inbound traffic exceeds this value, blackholing is triggered.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15694/15452113687339_en-US.png)


## Allow read-only access to Anti-DDoS Basic {#section_c4n_wjc_wdb .section}

To allow read-only access to Anti-DDoS Basic, complete these steps:

**Note:** Use the primary account to complete the authorization.

1.  Use the primary account to log on to the RAM console.
2.  In the left-side navigation pane, click **Users**, find the target RAM user and click **Manage**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/4157/15452113692872_en-US.png)

3.  Click **User Authorization Policies**, and then click **Edit Authorization Policy**.
4.  In the displayed dialog box, search **AliyunYundunDDosReadOnlyAccess**, and then add it to the Selected Authorization Policy Name list. Click **OK**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/4157/15452113692873_en-US.png)


## View the security credit score {#section_chv_cjy_gfb .section}

The security credit score is provided by Alibaba Cloud based on your attack history, purchase history, account activity, security level, expectation and more. With a higher security credit score, you can have a higher free blackholing threshold and a shorter blackholing duration \(how long the blackholing status lasts\).

Complete these steps to view the security credit score:

1.  Log on to the [Anti-DDoS Basic console](https://partners-intl.console.aliyun.com/?p=ddosnext#/instance).
2.  Select **Anti-DDoS Basic** \> **Instances**.
3.  Click the **Security Credibility** link to view the security credit score of the account.

    **Note:** Security credit scores are region-based.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15694/154521136912959_en-US.png)


