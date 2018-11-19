# CreateRules {#reference_dzs_pd2_ndb .reference}

为指定的HTTP/HTTPS监听添加转发规则。

## 调试 {#section_bk3_ybb_rfb .section}

```
点击[这里](https://api.aliyun.com/#product=Slb&api=CreateRules)在OpenAPI Explorer中可视化调试，并自动生成SDK调用示例。
```

## 请求参数 {#section_v5w_nds_cz .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|要执行的操作，取值：CreateRules

|
|RegionId|String|是|负载均衡实例的地域ID。您可以通过调用 DescribeRegions接口获取地域ID。

|
|LoadBalancerId|String|是|负载均衡实例ID。|
|ListenerPort|String|是|负载均衡实例前端使用的监听端口。取值范围：1-65535

|
|RuleList|List|是|要添加的转发规则。**说明：** 一次请求中，最多可添加10条转发规则。

|

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|RuleName|String|是|转发规则名称。长度限制为1-80，只能使用字母、数字、‘-’、‘/’、‘.’、‘\_’这些字符。

**说明：** 同一个监听内不同规则的名称必须唯一。

|
|Domain|String|否|请求域名。域名只能使用字母、数字、连字符（-）、点（.）。

|
|Url|String|否|访问路径。长度限制为1-80，只能使用字母、数字、‘-’、‘/’、‘.’、‘%’、‘?’、‘\#’、‘&’这些字符。

**说明：** Domain和Url两者必传其一，也可都传。Domain和Url的组合在同一个监听内必须唯一。

|
|VServerGroupId|String|是|该转发规则关联的服务器组ID。|

## 返回参数 {#section_ssd_pds_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|Rules|List|转发规则列表。|

|名称|类型|描述|
|:-|:-|:-|
|RuleId|String|转发规则 ID。|
|RuleName|String|转发规则名称。|

## 示例 {#section_oxr_pds_cz .section}

**请求示例**

``` {#public}
https://slb.aliyuncs.com/?Action=CreateRules
&RegionId=cn-hangzhou
&LoadBalancerId=lb-t4nj5vuz8ish9emfk1f20
&ListenerPort=80
&Rules=[
    {"RuleName":"Rule1","Domain":"abcdefg.com","Url":"/image","VServerGroupId":"Group1"},
    {"RuleName":"Rule2","Domain":"abcdefg.com","Url":"/cache","VServerGroupId":"Group2"},
  ]
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="utf-8"?>
    <CreateRulesResponse>
    	<RequestId>9DEC9C28-AB05-4DDF-9A78-6B08EC9CE18C</RequestId>
    	<Rules>
    		<Rule>
    			<RuleId>rule-3ejhktkaeu</RuleId>
    			<RuleName>Rule1</RuleName>
    		</Rule>
    		<Rule>
    			<RuleId>rule-tybqi6qkp8</RuleId>
    			<RuleName>Rule2</RuleName>
    		</Rule>
    	</Rules>
    </CreateRulesResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId": "9DEC9C28-AB05-4DDF-9A78-6B08EC9CE18C",
      "Rules": {
        "Rule": [
          {
            "RuleId": "rule-3ejhktkaeu",
            "RuleName": "Rule1"
          },
          {
            "RuleId": "rule-tybqi6qkp8",
            "RuleName": "Rule2"
          }
        ]
      }
    }
    ```


