# DescribeRules {#reference_nhj_wg2_ndb .reference}

查询指定监听已配置的转发规则。

## 调试 {#section_kdb_vcb_rfb .section}

```
点击[这里](https://api.aliyun.com/#product=Slb&api=DescribeRules)在OpenAPI Explorer中可视化调试，并自动生成SDK调用示例。
```

## 请求参数 {#section_v5w_nds_cz .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|要执行的操作，取值：DescribeRules

|
|RegionId|String|是|负载均衡实例的地域ID。|
|LoadBalancerId|String|是|负载均衡实例ID。您可以通过调用 DescribeRegions接口获取地域ID。

|
|ListenerPort|String|是|负载均衡实例前端使用的监听端口。取值：1-65535

|

## 返回参数 {#section_ssd_pds_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|Rules|String|规则列表。|

|名称|类型|描述|
|:-|:-|:-|
|RuleId|String|转发规则ID。|
|RuleName|String|转发规则名称。|
|Domain|String|域名。|
|Url|String|访问路径。|
|VServerGroupId|String|该转发规则的目标服务器组ID。|

## 示例 {#section_oxr_pds_cz .section}

**请求示例**

``` {#public}
https://slb.aliyuncs.com/?Action=DescribeRules
&RegionId=cn-hangzhou
&LoadBalancerId=lb-152a602e315
&ListenerPort=80
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="utf-8"?>
    <DescribeRulesResponse>	
        <RequestId>C9E4B5F7-1AA8-4578-9D59-8525C32BAD41</RequestId>
    	<Rules>
    		<Rule>
    			<Url>/index</Url>
    			<Domain>example.com</Domain>
    			<VServerGroupId>rsp-bp1t8kkfafu8b</VServerGroupId>
    			<RuleId>rule-bp1ixgmll8x92</RuleId>
    			<RuleName>test</RuleName>
    		</Rule>
    		<Rule>
    			<Url>/index</Url>
    			<Domain>test.com</Domain>
    			<VServerGroupId>rsp-bp1t8kkfafu8b</VServerGroupId>
    			<RuleId>rule-bp16ryrpwbg01</RuleId>
    			<RuleName>test2</RuleName>
    		</Rule>
    	</Rules>
    </DescribeRulesResponse>
    ```

-   JSON格式

    ```
    {
       "RequestId":"C9E4B5F7-1AA8-4578-9D59-8525C32BAD41",
       "Rules":{
          "Rule":[
             {
                "Url":"/index",
                "Domain":"example.com",
                "VServerGroupId":"rsp-bp1t8kkfafu8b",
                "RuleId":"rule-bp1ixgmll8x92",
                "RuleName":"test"
             },
             {
                "Url":"/index",
                "Domain":"test.com",
                "VServerGroupId":"rsp-bp1t8kkfafu8b",
                "RuleId":"rule-bp16ryrpwbg01",
                "RuleName":"test2"
             }
          ]
       }
    }
    ```


