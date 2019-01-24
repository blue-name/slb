# AddListenerWhiteListItem {#doc_api_952775 .reference}

调用AddListenerWhiteListItem添加监听访问控制白名单。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Slb&api=AddListenerWhiteListItem)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|AddListenerWhiteListItem|要执行的操作。

 取值：**AddListenerWhiteListItem**

 |
|ListenerPort|Integer|是|80|负载均衡实例前端使用的端口。

 |
|LoadBalancerId|String|是|139a00604ad-cn-east-hangzhou-01|负载均衡实例的ID。

 |
|RegionId|String|是|cn-hangzhou|实例所在地域。

 |
|SourceItems|String|是|1.1.1.1,1.1.1.0/21|访问控制列表。

 监听的**AccessControlStatus**为**open\_white\_list**时有效。

 支持输入IP地址或IP地址段（CIDR block形式），多个IP地址或地址段用逗号（,）分割。

 不允许输入0.0.0.0或0.0.0.0/0。您可以通过调用[SetListenerAccessControlStatus](~~27599~~)接口将AccessControlStatus的值设置为close，关闭访问控制。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|CEF72CEB-54B6-4AE8-B225-F876FF7BA984|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=AddListenerWhiteListItem
&ListenerPort=80
&LoadBalancerId=139a00604ad-cn-east-hangzhou-01
&SourceItems=1.1.1.1,1.1.1.0/21
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<AddListenerWhiteListItemResponse>
  <RequestId>CEF72CEB-54B6-4AE8-B225-F876FF7BA984</RequestId>
</AddListenerWhiteListItemResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":" CEF72CEB-54B6-4AE8-B225-F876FF7BA984"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/Slb)

