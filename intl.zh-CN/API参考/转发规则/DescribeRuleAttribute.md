# DescribeRuleAttribute {#reference_fyc_mv2_ndb .reference}

查询指定转发规则的配置详情。

## 调试 {#section_agz_rcb_rfb .section}

```
点击[这里](https://api.aliyun.com/#product=Slb&api=DescribeRuleAttribute)在OpenAPI Explorer中可视化调试，并自动生成SDK调用示例。
```

## 请求参数 {#section_v5w_nds_cz .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|要执行的操作，取值：DescribeRuleAttribute

|
|RegionId|String|是|负载均衡实例的地域ID。您可以通过调用 DescribeRegions接口获取地域ID。

|
|RuleId|String|是|转发规则ID。|

## 返回参数 {#section_ssd_pds_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|RuleName|String|转发规则名称。|
|LoadBalancerId|String|负载均衡实例ID。|
|ListenerPort|Integer|负载均衡实例前端使用的监听端口。|
|Domain|String|转发规则域名。|
|Url|String|转发规则路径。|
|VServerGroupId|String|转发规则关联的服务器组ID。|

## 示例 {#section_oxr_pds_cz .section}

**请求示例**

``` {#public}
https://slb.aliyuncs.com/?Action=DescribeRuleAttribute
&RegionId=cn-hangzhou 
&RuleId=rule-3ejhktkaeu
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="utf-8"?>
    <DescribeRuleAttributeResponse>
    	<RequestId>3E0FA650-1843-466E-8664-3E7D88E0DD5F</RequestId>
    	<Domain>example.com</Domain>
    	<Url>/index</Url>
    	<VServerGroupId>rsp-bp1t8kkfafu8b</VServerGroupId>
    	<LoadBalancerId>lb-bp148m1ohj2juoh9ua7qc</LoadBalancerId>
    	<RuleName>test</RuleName>
    	<ListenerPort>8080</ListenerPort>
    </DescribeRuleAttributeResponse>
    ```

-   JSON格式

    ```
    {  
       "RequestId":"3E0FA650-1843-466E-8664-3E7D88E0DD5F",
       "Domain":"example.com",
       "Url":"/index",
       "VServerGroupId":"rsp-bp1t8kkfafu8b",
       "LoadBalancerId":"lb-bp148m1ohj2juoh9ua7qc",
       "RuleName":"test",
       "ListenerPort":8080
    }}
    ```


