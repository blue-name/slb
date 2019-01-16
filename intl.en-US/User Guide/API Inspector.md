# API Inspector {#concept_kpn_tls_2gb .concept}

API Inspector is an experimental feature. It enables you to view the API calls behind each step on the console, and automatically generates API codes of different languages. You can debug online through Cloud Shell or API Explorer.

## Features {#section_jy1_xls_2gb .section}

API Inspector, API Explorer, and Cloud Shell form an integrated solution for you to learn and debug API. It has the following features:

-   Automatic recording: To obtain related API calls, you only need to perform operations on the console. For more information, see [Automatically record API calling](#section_olp_yls_2gb).
-   Code generation with one click: API code scripts in different languages with pre-filled parameters are generated and can be run directly. For more information, see [Generate API codes with one click](#section_cyh_1ms_2gb).
-   Online debugging: When API Inspector is used together with API Explorer and Cloud Shell, one-click online debugging can be implemented and you do not need to build the development environment. What you get is what you see. For more information, see [Debug online through API Explorer](#section_vxc_gms_2gb) and [Debug online through Cloud Shell](#section_rvx_dms_2gb).

## Enable API Inspector {#section_jdj_qns_2gb .section}

To enable API Inspector, complete these steps:

1.  Log on to the [SLB console](https://slb.console.aliyun.com/slb).
2.  In the left-side navigation pane, select **SLB Lab** \> **API Inspector**.
3.  On the API Inspector page, enable API Inspector. Then the API suspended pendant is displayed on the right side of the page.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/81371/154762143534800_en-US.png)


## Automatically record API calling {#section_olp_yls_2gb .section}

Modifying the name of an SLB instance is taken as an example to demonstrate the automatic recording function of API Inspector.

1.  Select **Instances** \> **Server Load Balancer**.
2.  Modify the name of an SLB instance to **SLB1**.
3.  Click **OK**.
4.  Click **![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/81371/154762143534810_en-US.png)** on the right side of the page. Then you can see all API calls related to the preceding operation.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/81371/154762143534821_en-US.png)

5.  You can click **Hide Describe Class OpenAPI Explorer** to view core APIs. In the example, the core API is SetLoadBalancerName.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/81371/154762143534825_en-US.png)


## Generate API codes with one click {#section_cyh_1ms_2gb .section}

After API recording is completed, click the API name to generate API code scripts in Python, Java, Go, Node.js, and PHP, with pre-filled parameters.

**Note:** Click **![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/81371/154762143534833_en-US.png)** to copy the code scripts of the corresponding format, which can be run directly.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/81371/154762143534832_en-US.png)

## Debug online through API Explorer {#section_vxc_gms_2gb .section}

After the API recording is completed, click **OpenAPI Explorer** or **![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/81371/154762143534835_en-US.png)** to go to the [OpenAPI Explorer console](https://api.aliyun.com/#product=Slb&api=SetLoadBalancerName) to debug the corresponding function. The API parameter values have been automatically generated according to operations on the console.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/81371/154762143534837_en-US.png)

**Note:** Click **![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/81371/154762143534836_en-US.png)** to view the document describing the parameter details of the called API.

## Debug online through Cloud Shell {#section_rvx_dms_2gb .section}

After API recording, unfold the API calling details and click **![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/81371/154762143534846_en-US.png)** to use the online one-click debugging of Cloud Shell.

**Note:** If you use the one-click debugging of Cloud Shell, we recommend that you associate and create an OSS Bucket to store your frequently used scripts and files. However, a small amount of OSS costs will be generated. You can also choose to do not create an OSS Bucket.

The cloud command line format for the Cloud Shell debugging of SLB is as follows:

```
aliyun slb actionName --parameter1 value1 --paramter2 value2...
```

In this example, the called SetLoadBalancerName API modifies the name of the SLB instance to SLB1, so run the following cloud command line:

```
aliyun slb SetLoadBalancerName --RegionId cn-hangzhou --LoadBalancerName SLB1 --LoadBalancerId lb-bp1b6c719dfa08exfuca5
```

The returned value is:

```
{"RequestId":"14466282-B00F-49C1-B11E-FB8D3772E3DA"}
```

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/81371/154762143534847_en-US.png)

