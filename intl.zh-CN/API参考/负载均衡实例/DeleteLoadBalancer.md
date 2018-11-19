# DeleteLoadBalancer {#doc_api_712601 .reference}

删除后付费的负载均衡实例， 在负载均衡实例中配置的监听和后端服务器配置也会删除。

**说明：** 如果负载均衡实例上还有监听或者绑定了相应的标签，也会一并被删除。

## 调试 {#section_pjn_3v5_qfb .section}

```
点击[这里](https://api.aliyun.com/#product=Slb&api=DeleteLoadBalancer)在OpenAPI Explorer中可视化调试，并自动生成SDK调用示例。
```

## 请求参数 {#section_bqw_c1g_cz .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|要执行的操作。 取值： DeleteLoadBalancer

|
|RegionId|String|是|负载均衡实例的地域。您可以通过调用 DescribeRegions接口获取地域ID。

|
|LoadBalancerId|String|是|负载均衡实例的ID。|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|说明|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#public}
https://slb.aliyuncs.com/?Action=DeleteLoadBalancer
&LoadBalancerId=lb-t4nj5vuz8ish9emfk1f20
&RegionId=ap-southeast-1
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DeleteLoadBalancerResponse>
    	<RequestId>CEF72CEB-54B6-4AE8-B225-F876FF7BA984</RequestId>
    </DeleteLoadBalancerResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId": " CEF72CEB-54B6-4AE8-B225-F876FF7BA984"
    }
    ```


