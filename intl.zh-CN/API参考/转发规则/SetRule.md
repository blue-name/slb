# SetRule {#reference_hsd_jg2_ndb .reference}

更改转发规则的目标服务器组。

## 调试 {#section_rch_mcb_rfb .section}

```
点击[这里](https://api.aliyun.com/#product=Slb&api=SetRule)在OpenAPI Explorer中可视化调试，并自动生成SDK调用示例。
```

## 请求参数 {#section_v5w_nds_cz .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|要执行的操作，取值：SetRule

|
|RegionId|String|是|负载均衡实例的地域ID。您可以通过调用 DescribeRegions接口获取地域ID。

|
|RuleId|String|是|转发规则ID。|
|VServerGroupId|String|是|转发规则的目标服务器组ID。|

## 返回参数 {#section_ssd_pds_cz .section}

|参数|类型|说明|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_oxr_pds_cz .section}

**请求示例**

``` {#public}
https://slb.aliyuncs.com/?Action=SetRule
&RegionId=cn-hangzhou
&RuleId=[rule-3ejhktkaeu &VServerGroupId=rsp-cige6j5e7p]
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="utf-8"?>
    <SetRuleResponse>
    	<RequestId>9DEC9C28-AB05-4DDF-9A78-6B08EC9CE18C</RequestId>
    </SetRuleResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId":"9DEC9C28-AB05-4DDF-9A78-6B08EC9CE18C"
    }
    ```


