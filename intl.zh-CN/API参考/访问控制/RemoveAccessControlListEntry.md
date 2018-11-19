# RemoveAccessControlListEntry {#reference_n2r_h4v_tdb .reference}

删除访问控制策略组中的IP条目。

## 调试 {#section_bfx_v3b_rfb .section}

```
点击[这里](https://api.aliyun.com/#product=Slb&api=RemoveAccessControlListEntry)在OpenAPI Explorer中可视化调试，并自动生成SDK调用示例。
```

## 请求参数 {#section_n4h_pyx_5db .section}

|参数|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|要执行的操作，取值：RemoveAccessControlListEntry

|
|RegionId|String|是|访问控制策略组的地域ID。|
|AclId|String|是|访问控制策略组ID。|
|AclEntrys|String|否| 访问控制策略组中要添加的IP条目，可以指定IP地址或IP地址段（CIDR block），多个IP地址/地址段之间用逗号隔开。比如：

 \[\{“entry”:”10.0.0.1”,”comment”:”条目1”\},\{“entry”:”192.168.0.0/16”,”comment”:”条目2”\}\]

 **说明：** 如果访问控制策略组关联了监听，不允许删除组内的所有IP条目。

 |

## 返回参数 {#section_ehc_jzx_5db .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_oxr_pds_cz .section}

**请求示例**

```
https://slb.aliyuncs.com/?Action=RemoveAccessControlListEntry
&RegionId=us-west-1
&AclId=acl-rj9xpxzcwxrukois65yw3
&AclEntrys=[{"entry":"10.0.0.1","comment":"条目1"}]
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="utf-8"?>
    <RemoveAccessControlListEntryResponse>
      <RequestId>988CB45E-1643-48C0-87B4-928DDF77EA49</RequestId>
    </RemoveAccessControlListEntryResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "988CB45E-1643-48C0-87B4-928DDF77EA49"
    }
    ```


