# RemoveTags {#reference_zdx_mff_ndb .reference}

解绑负载均衡实例的标签。

## 调试 {#section_vvj_mz1_rfb .section}

```
点击[这里](https://api.aliyun.com/#product=Slb&api=RemoveTags)在OpenAPI Explorer中可视化调试，并自动生成SDK调用示例。
```

## 请求参数 {#section_v5w_nds_cz .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|要执行的操作，取值：RemoveTags

|
|RegionId|String|是|负载均衡地域。您可以通过调用 DescribeRegions接口获取地域ID。

|
|LoadBalancerID|String|是|负载均衡实例ID。|
|Tags|String|否|需要解绑的Tag列表。|

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|TagKey|String|是|标签的键值。最多支持64个字，不能以aliyun开头，不允许为空。

|
|TagValue|String|否|标签的值。最多支持128个字符， 不能以aliyun开头。

|

## 返回参数 {#section_ssd_pds_cz .section}

|名称|类型|说明|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_oxr_pds_cz .section}

**请求示例**

``` {#public}
https://slb.aliyuncs.com/?Action=RemoveTags
&RegionId=cn-hangzhou
&LoadBalancerId=lb-t4nj5vuz8ish9emfk1f20
&Tags=[
    {"TagKey":"Key1","TagValue":"Value1"}    
    {"TagKey":"Key2","TagValue":"Value2"}]
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <RemoveTagsResponse>
    	<RequestId>365F4154-92F6-4AE4-92F8-7FF34B540710</RequestId>
    </RemoveTagsResponse>
    ```

-   JSON格式

    ```
     {
      "RequestId":"365F4154-92F6-4AE4-92F8-7FF34B540710",
    }
    ```


