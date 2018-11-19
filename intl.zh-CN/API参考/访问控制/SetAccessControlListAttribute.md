# SetAccessControlListAttribute {#reference_n2r_h4v_tdb .reference}

修改访问控制策略组的名称。

## 调试 {#section_b3h_p3b_rfb .section}

```
点击[这里](https://api.aliyun.com/#product=Slb&api=SetAccessControlListAttribute)在OpenAPI Explorer中可视化调试，并自动生成SDK调用示例。
```

## 请求参数 {#section_n4h_pyx_5db .section}

|参数|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|要执行的操作，取值：SetAccessControlListAttribute

|
|RegionId|String|是|访问控制策略组的地域ID。|
|AclId|String|是|访问控制策略组ID。|
|AclName|String|是|访问控制策略组名称。|

## 返回参数 {#section_ehc_jzx_5db .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_oxr_pds_cz .section}

**请求示例**

```
https://slb.aliyuncs.com/?Action=SetAccessControlListAttribute
&RegionId=us-west-1
&AclId=acl-rj9xpxzcwxrukois65yw3
&AclName=test
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="utf-8"?>
    <SetAccessControlListAttributeResponse>
      <RequestId>988CB45E-1643-48C0-87B4-928DDF77EA49</RequestId>
    </SetAccessControlListAttributeResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "988CB45E-1643-48C0-87B4-928DDF77EA49"
    }
    ```


