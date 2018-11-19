# DescribeAccessControlLists {#reference_n2r_h4v_tdb .reference}

查询已创建的访问控制策略组。

## 调试 {#section_lyv_b3b_rfb .section}

```
点击[这里](https://api.aliyun.com/#product=Slb&api=DescribeAccessControlLists)在OpenAPI Explorer中可视化调试，并自动生成SDK调用示例。
```

## 请求参数 {#section_n4h_pyx_5db .section}

|参数|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|要执行的操作，取值：DescribeAccessControlLists

|
|RegionId|String|是|访问控制策略组的地域ID。|
|AclName|String|否|访问控制策略组名称。|

## 返回参数 {#section_ehc_jzx_5db .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|AclId|String|访问控制策略组ID。|
|AclName|String|访问控制策略组名称。|

## 示例 {#section_oxr_pds_cz .section}

**请求示例**

```
https://slb.aliyuncs.com/?Action=DescribeAccessControlLists
&RegionId=en-west-1
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="utf-8"?>
    <DescribeAccessControlListsResponse>
     <Acls>
        <Acl>
              <AclId>acl-rj9wmaq1up8wfy3nr8pzm</AclId>
              <AclName>test</AclName>
        </Acl>
     </Acls>
     <RequestId>F7C4E504-2D62-45E8-9017-336F2FF75A2A</RequestId>
    </DescribeAccessControlListsResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId": "F7C4E504-2D62-45E8-9017-336F2FF75A2A",
      "Acls": {
          "Acl": [
              {
                  "AclId": "acl-rj9wmaq1up8wfy3nr8pzm",
                  "AclName": "test"
              }
          ]
      }
    }
    ```


