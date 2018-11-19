# DescribeVServerGroups {#reference_fy2_gvd_ddd .reference}

查询已创建的服务器组。

## 调试 {#section_qyy_l11_rfb .section}

```
点击[这里](https://api.aliyun.com/#product=Slb&api=DescribeVServerGroups)在OpenAPI Explorer中可视化调试，并自动生成SDK调用示例。
```

## 请求参数 {#section_v5w_nds_cz .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|要执行的操作，取值：DescribeVServerGroups

|
|RegionId|String|是|负载均衡实例的地域ID。您可以通过调用 DescribeRegions接口获取地域ID。

|
|LoadBalancerId|String|是|负载均衡实例ID。|
|**IncludeRule**|Boolean|否|返回关联的转发规则信息，默认值：false

|
|**IncludeListener**|Boolean|否|返回关联的监听信息，默认值：false

|

## 返回参数 {#section_ssd_pds_cz .section}

|名称|类型|描述|
|--|--|--|
|**RequestId**|String|请求ID。|
|**VServerGroups**|List|虚拟服务器组列表。|

|名称|类型|描述|
|:-|:-|:-|
|VServerGroupId|String|服务器组ID。|
|VServerGroupName|String|服务器组名称。|
|**AssociatedObjects**|Object|关联信息。|

|名称|类型|描述|
|:-|:-|:-|
|Rules|List|转发规则列表。|
|Listeners|List|监听列表。|

|名称|类型|描述|
|--|--|--|
|RuleId|String|转发规则ID。|
|RuleName|String|转发规则名称。|
|Domain|String|请求域名。|
|Url|String|访问路径。|

|名称|类型|描述|
|--|--|--|
|Protocol|String|监听协议。|
|Port|Integer|监听端口。|

## 示例 {#section_oxr_pds_cz .section}

**请求示例**

``` {#public}
https://slb.aliyuncs.com/?Action=DescribeVServerGroups
&RegionId=cn-hangzhou
&LoadBalancerId=lb-bp1yii0s312x83r3qpzke
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    	<VServerGroups>
    		<VServerGroup>
    			<VServerGroupId>rsp-bp12bjrnykyp0</VServerGroupId>
    			<VServerGroupName>6</VServerGroupName>
    			<AssociatedObjects>
    				<Listeners></Listeners>
    				<Rules></Rules>
    			</AssociatedObjects>
    		</VServerGroup>
    		<VServerGroup>
    			<VServerGroupId>rsp-bp16rt0dzbm23</VServerGroupId>
    			<VServerGroupName>text2</VServerGroupName>
    			<AssociatedObjects>
    				<Listeners></Listeners>
    				<Rules></Rules>
    			</AssociatedObjects>
    		</VServerGroup>
    	</VServerGroups>
    	<RequestId>E3F94C66-5DDD-4A6B-B37D-FD237FB31FE6</RequestId>
    ```

-   JSON格式

    ```
    {
        "VServerGroups": {
            "VServerGroup": [
                {
                    "VServerGroupId": "rsp-bp12bjrnykyp0", 
                    "VServerGroupName": "6", 
                    "AssociatedObjects": {
                        "Listeners": {
                            "Listener": [ ]
                        }, 
                        "Rules": {
                            "Rule": [ ]
                        }
                    }
                }, 
                {
                    "VServerGroupId": "rsp-bp16rt0dzbm23", 
                    "VServerGroupName": "text2", 
                    "AssociatedObjects": {
                        "Listeners": {
                            "Listener": [ ]
                        }, 
                        "Rules": {
                            "Rule": [ ]
                        }
                    }
                }
            ]
        }, 
        "RequestId": "E3F94C66-5DDD-4A6B-B37D-FD237FB31FE6"
    }
    ```


