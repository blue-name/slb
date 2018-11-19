# DeleteMasterSlaveServerGroup {#reference_fvz_rxd_ndb .reference}

删除指定的主备服务器组。

## 调试 {#section_psc_dy1_rfb .section}

```
点击[这里](https://api.aliyun.com/#product=Slb&api=DeleteMasterSlaveServerGroup)在OpenAPI Explorer中可视化调试，并自动生成SDK调用示例。
```

## 请求参数 {#section_v5w_nds_cz .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|要执行的操作，取值：DeleteMasterSlaveServerGroup

|
|RegionId|String|是|负载均衡地域。您可以通过调用 DescribeRegions接口获取地域ID。

|
|MasterSlaveServerGroupId|String|是|要删除的主备服务器组的ID。**说明：** 如果要删除的服务器组正在使用中，无法删除。

|

|名称|类型|说明|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 返回参数 {#section_ssd_pds_cz .section}

## 示例 {#section_oxr_pds_cz .section}

**请求示例**

``` {#public}
https://slb.aliyuncs.com/?Action=CreateMasterSlaveServerGroup
&RegionId=cn-hangzhou
&LoadBalancerId=lb-t4nj5vuz8ish9emfk1f20
&MasterSlaveServerGroupName=Group1
&MasterSlaveBackendServers=[
    {"ServerId":"vm-233","Port":"80","Weight":"100","ServerType":"Master"},
    {"ServerId":"vm-232","Port":"90","Weight":"100","ServerType":"Slave"},
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="utf-8"?>
    <DeleteMasterSlaveServerGroupResponse>
    	<RequestId>9DEC9C28-AB05-4DDF-9A78-6B08EC9CE18C</RequestId>
    </DeleteMasterSlaveServerGroupResponse>
    ```

-   JSON格式

    ```screen
    {
      "RequestId":"9DEC9C28-AB05-4DDF-9A78-6B08EC9CE18C"
    }
    ```


