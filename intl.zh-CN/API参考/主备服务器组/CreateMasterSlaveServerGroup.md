# CreateMasterSlaveServerGroup {#reference_qky_rwd_ndb .reference}

创建主备服务器组。一组主备服务器组只能包含两个ECS实例，一个为主服务器，另一个为备服务器。

## 调试 {#section_grq_zx1_rfb .section}

```
点击[这里](https://api.aliyun.com/#product=Slb&api=CreateMasterSlaveServerGroup)在OpenAPI Explorer中可视化调试，并自动生成SDK调用示例。
```

## 请求参数 {#section_v5w_nds_cz .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|要执行的操作，取值：CreateMasterSlaveServerGroup

|
|RegionId|String|是|负载均衡地域。您可以通过调用 DescribeRegions接口获取地域ID。

|
|LoadBalancerId|String|是|负载均衡实例ID。|
|MasterSlaveServerGroupName|String|否|主备服务器组名称。|
|MasterSlaveBackendServers|List|是|主备服务器组列表。一个主备服务器组最多可包含2个后端服务器。

如果不指定该参数，则创建一个空的主备服务器组列表。

|

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|ServerId|String|是|ECS实例ID。|
|Port|String|是|后端服务器使用的端口。取值范围：1-65535

|
|Weight|String|是|后端服务器的权重，取值：\[0,100\]默认值为100。如果值为0，则不会将请求转发给该后端服务器。

|
|ServerType|String|是|服务器类型，取值：Master（默认值） | Slave

|
|Type|String|是|后端服务器类型，取值：-   ecs：ECS实例（默认）
-   eni：弹性网卡实例

|

## 返回参数 {#section_ssd_pds_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|MasterSlaveServerGroupId|String|主备服务器组ID。|
|MasterSlaveBackendServers|List|主备服务器组列表。|

|名称|类型|描述|
|:-|:-|:-|
|ServerId|String|ECS实例ID。|
|Port|String|后端服务器使用的端口。取值范围：1-65535

|
|Weight|String|后端服务器的权重，取值：\[0,100\]默认值为100。如果值为0，则不会将请求转发给该后端服务器。

|
|ServerType|String|服务器类型，取值：Master（默认值） | Slave

|
|Type|String|后端服务器类型，取值：-   ecs：ECS实例（默认）
-   eni：弹性网卡实例

|

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
    <CreateMasterSlaveServerGroupResponse>
      <RequestId>9DEC9C28-AB05-4DDF-9A78-6B08EC9CE18C</RequestId>
      <MasterSlaveServerGroupId>rsp-cige6j5e7p</MasterSlaveServerGroupId>
      <MasterSlaveBackendServers>
          <MasterSlaveBackendServers>
              <ServerId>vm-233</ServerId>
              <Port>80</Port>
              <Weight>100</Weight>
              <ServerType>Master</ServerType>
          </MasterSlaveBackendServers>
          <MasterSlaveBackendServers>
              <ServerId>vm-232</ServerId>
              <Port>90</Port>
              <Weight>100</Weight>
              <ServerType>Slave</ServerType>
          </MasterSlaveBackendServers>
      </MasterSlaveBackendServers>
    </CreateMasterSlaveServerGroupResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId":"9DEC9C28-AB05-4DDF-9A78-6B08EC9CE18C",
      "MasterSlaveServerGroupId":"rsp-cige6j5e7p",
      "MasterSlaveBackendServers":{
          "MasterSlaveBackendServers":[
            {"ServerId":"vm-233","Port":"80","Weight":"100","ServerType":"Master"},
            {"ServerId":"vm-232","Port":"90","Weight":"100","ServerType":"Slave"},
          ]
        }
    }
    ```


