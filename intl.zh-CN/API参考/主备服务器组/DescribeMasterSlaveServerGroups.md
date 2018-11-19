# DescribeMasterSlaveServerGroups {#reference_jn1_kzd_ndb .reference}

查询已创建的主备服务器组。

## 调试 {#section_zbx_bz1_rfb .section}

```
点击[这里](https://api.aliyun.com/#product=Slb&api=DescribeMasterSlaveServerGroups)在OpenAPI Explorer中可视化调试，并自动生成SDK调用示例。
```

## 请求参数 {#section_v5w_nds_cz .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|要执行的操作，取值：DescribeMasterSlaveServerGroups

|
|RegionId|String|是|负载均衡地域。您可以通过调用 DescribeRegions接口获取地域ID。

|
|LoadBalancerId|String|是|负载均衡实例ID。|
|IncludeListener|Boolean|否|是否返回关联的监听信息，默认值：false

|

## 返回参数 {#section_ssd_pds_cz .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|请求ID。|
|MasterSlaveServerGroups|List|主备服务器组列表。|

|名称|类型|描述|
|:-|:-|:-|
|MasterSlaveServerGroupId|String|主备服务器组ID。|
|MasterSlaveServerGroupName|String|主备服务器组名称。|
|AssociatedObjects|Object|关联信息。|

|名称|类型|描述|
|:-|:-|:-|
|Listeners|List|监听列表。|

|名称|类型|描述|
|:-|:-|:-|
|Protocol|String|监听协议。|
|Port|Integer|监听端口。|

## 示例 {#section_oxr_pds_cz .section}

**请求示例**

``` {#public}
https://slb.aliyuncs.com/?Action=DescribeMasterSlaveServerGroups
&RegionId=cn-hangzhou
&LoadBalancerId=lb-t4nj5vuz8ish9emfk1f20
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="utf-8"?>
    <DescribeMasterSlaveServerGroupsResponse>
        <RequestId>2631BB5E-B576-4925-BDED-07A66D23E5DE</RequestId>
        <MasterSlaveServerGroups>
    	<MasterSlaveServerGroup>
    		<MasterSlaveServerGroupId>rsp-bp1ro3mwp2x2m</MasterSlaveServerGroupId>
    		<MasterSlaveServerGroupName>test</MasterSlaveServerGroupName>
    	</MasterSlaveServerGroup>
        </MasterSlaveServerGroups>
    </DescribeMasterSlaveServerGroupsResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId": "2631BB5E-B576-4925-BDED-07A66D23E5DE",
      "MasterSlaveServerGroups": {
        "MasterSlaveServerGroup": [
          {
            "MasterSlaveServerGroupId": "rsp-bp1ro3mwp2x2m",
            "MasterSlaveServerGroupName": "test"
          }
        ]
      }
    }
    ```


