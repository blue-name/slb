# SetListenerAccessControlStatus {#slb_api_SetListenerAccessControlStatus .reference}

为指定监听开启或关闭访问控制功能。

## 调试 {#section_gx3_qwz_qfb .section}

```
点击[这里](https://api.aliyun.com/#product=Slb&api=SetListenerAccessControlStatus)在OpenAPI Explorer中可视化调试，并自动生成SDK调用示例。
```

## 请求参数 {#section_v5w_nds_cz .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|要执行的操作，取值：SetListenerAccessControlStatus

|
|RegionId|String|是|负载均衡实例的地域。您可以通过调用 DescribeRegions接口获取地域ID。

|
|LoadBalancerId|String|是|负载均衡实例的ID。|
|ListenerPort|Integer|是|负载均衡实例前端使用的端口。取值：1-65535

|
|AccessControlStatus|String|是|是否开启访问控制。取值：-   open\_white\_list：开启访问控制。
-   close：关闭访问控制。

**说明：** 如果开启访问控制后，没有设置白名单则无法访问负载均衡服务。

|

## 返回参数 {#section_ssd_pds_cz .section}

|名称|类型|说明|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_oxr_pds_cz .section}

**请求示例**

``` {#public}
https://slb.aliyuncs.com/?Action=SetListenerAccessControlStatus
&LoadBalancerId=lb-t4nj5vuz8ish9emfk1f20
&ListenerPort=80
&AccessControlStatus=open_white_list
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <SetListenerAccessControlStatusResponse>
          <RequestId>CEF72CEB-54B6-4AE8-B225-F876FF7BA984</RequestId>
    </SetListenerAccessControlStatusResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId":" CEF72CEB-54B6-4AE8-B225-F876FF7BA984"
    }
    ```


