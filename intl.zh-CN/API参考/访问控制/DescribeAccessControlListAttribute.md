# DescribeAccessControlListAttribute {#reference_n2r_h4v_tdb .reference}

查询访问控制策略组的配置。

## 调试 {#section_pxk_m3b_rfb .section}

```
点击[这里](https://api.aliyun.com/#product=Slb&api=DescribeAccessControlListAttribute)在OpenAPI Explorer中可视化调试，并自动生成SDK调用示例。
```

## 请求参数 {#section_n4h_pyx_5db .section}

|参数|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|要执行的操作，取值：DescribeAccessControlListAttribute

|
|RegionId|String|是|访问控制策略组的地域ID。|
|AclId|String|是|访问控制策略组ID。|
|AclEntryComment|String|否|访问控制策略组中的路由条目的说明信息。|

## 返回参数 {#section_ehc_jzx_5db .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|AclId|String|访问控制策略组ID。|
|AclName|String|访问控制策略组名称。|
|AclEntrys|List|访问控制策略组中的IP条目。|
|RelatedListeners|List|访问控制策略关联的监听。|

|名称|类型|描述|
|:-|:-|:-|
|AclEntryIP|String|访问控制条目IP。|
|AclEntryComment|String|访问控制条目备注。|

|名称|类型|描述|
|:-|:-|:-|
|LoadBalancerId|String|负载均衡实例ID。|
|ListenerPort|Integer|监听的前端端口。|
|Protocol|Integer|监听协议。|
|AclType|String|访问控制类型：-   black：黑名单
-   white：白名单

|

## 示例 {#section_oxr_pds_cz .section}

**请求示例**

```
https://slb.aliyuncs.com/?Action=DescribeAccessControlListAttribute
&RegionId=us-west-1
&AclId=acl-0xiowxdr4drxtm2w8hupo
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="utf-8"?>
    <DescribeAccessControlListAttributeResponse>
    <AclName>group1</AclName>
    <RequestId>6669026E-067E-47B6-8106-EA810382A3BB</RequestId>
    <AclEntrys>
      <AclEntry>
        <AclEntryComment>1,10.10.0.0/24</AclEntryComment>
        <AclEntryIP>10.10.0.0/24</AclEntryIP>
      </AclEntry>
    </AclEntrys>
    <AclId>acl-0xiowxdr4drxtm2w8hupo</AclId>
    <RelatedListeners>
      <RelatedListener>
        <AclType>white</AclType>
        <LoadBalancerId>lb-0xiw3x1ljvd2a5golok5v</LoadBalancerId>
        <Protocol>https</Protocol>
        <ListenerPort>443</ListenerPort>
      </RelatedListener>
    </RelatedListeners>
    </DescribeAccessControlListAttributeResponse>
    ```

-   JSON格式

    ```
    {
      "AclName": "group1",
      "RequestId": "6669026E-067E-47B6-8106-EA810382A3BB"
      "AclEntrys": {
          "AclEntry": [
              {
                  "AclEntryComment": "1,10.10.0.0/24",
                  "AclEntryIP": "10.10.0.0/24"
              }
          ]
        },
          "AclId": "acl-0xiowxdr4drxtm2w8hupo",
          "RelatedListeners": {
          "RelatedListener": [
              {
                  "AclType": "white",
                  "LoadBalancerId": "lb-0xiw3x1ljvd2a5golok5v",
                  "Protocol": "https",
                  "ListenerPort": 443
              }
          ]
      }
    }
    ```


