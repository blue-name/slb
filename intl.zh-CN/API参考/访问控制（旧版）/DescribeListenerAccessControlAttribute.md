# DescribeListenerAccessControlAttribute {#slb_api_DescribeListenerAccessControlAttribute .reference}

查询监听的访问控制配置。

## 调试 {#section_ihg_lwz_qfb .section}

```
点击[这里](https://api.aliyun.com/#product=Slb&api=DescribeListenerAccessControlAttribute)在OpenAPI Explorer中可视化调试，并自动生成SDK调用示例。
```

## 请求参数 {#section_v5w_nds_cz .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|要执行的操作，取值：DescribeListenerAccessControlAttribute

|
|LoadBalancerId|String|是|负载均衡实例的ID。|
|ListenerPort|Integer|是|负载均衡实例前端使用的端口。取值：1-65535

|

## 返回参数 {#section_ssd_pds_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|AccessControlStatus|String|是否开启访问控制，取值：-   open\_white\_list：开启访问控制。
-   close：关闭访问控制。

|
|SourceItems|String|访问控制列表。|

## 示例 {#section_oxr_pds_cz .section}

**请求示例**

``` {#public}
https://slb.aliyuncs.com/?Action=DescribeListenerAccessControlAttribute
&LoadBalancerId=lb-t4nj5vuz8ish9emfk1f20
&ListenerPort=80
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DescribeListenerAccessControlAttributeResponse>
    	<RequestId>365F4154-92F6-4AE4-92F8-7FF34B540710</RequestId>
    	<AccessControlStatus>open_white_list</AccessControlStatus>
    	<SourceItems>1.1.1.1,1.1.1.0/21</SourceItems>
    </DescribeListenerAccessControlAttributeResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId": "365F4154-92F6-4AE4-92F8-7FF34B540710",
      "AccessControlStatus": "open_white_list",
      "SourceItems": "1.1.1.1,1.1.1.0/21"
    }
    ```


