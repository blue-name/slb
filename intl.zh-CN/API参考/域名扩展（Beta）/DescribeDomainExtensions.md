# DescribeDomainExtensions {#reference_ds1_mfq_n2b .reference}

查询已添加的扩展域名。

## 调试 {#section_dgw_c1b_rfb .section}

```
点击[这里](https://api.aliyun.com/#product=Slb&api=DescribeDomainExtensions)在OpenAPI Explorer中可视化调试，并自动生成SDK调用示例。
```

## 请求参数 {#section_rm1_bcg_j2b .section}

|名称|类型|是否必选|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作，取值：

 DescribeDomainExtensions

 |
|RegionId|String|是|负载均衡实例的地域ID。|
|LoadBalancerId|String|是|负载均衡实例的ID。|
|ListenerPort|Integer|是| 负载均衡实例HTTPS监听的前端端口，取值：

 1-65535

 |
|DomainExtensionId|String|否|扩展域名ID。|

## 返回参数 {#section_xq3_scg_j2b .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|ListenerPort|Integer|负载均衡实例前端使用的端口。|
|LoadBalancerId|String|实例ID。|
|DomainExtensions|List|扩展域名列表。|

|名称|类型|描述|
|:-|:-|:-|
|DomainExtensionId|String|扩展域名ID。|
|Domain|Integer|域名。|
|ServerCertificateId|String|域名使用的证书ID。|

## 示例 {#section_oxr_pds_cz .section}

**请求示例**

``` {#public}
https://slb.aliyuncs.com/?Action=DescribeDomainExtensions
&RegionId=cn-hangzhou
&LoadBalancerId=lb-t4nj5vuz8ish9emfk1f20
&ListenerPort=443
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    <SetDomainExtensionAttributeResponseResponse>
    	<RequestId>149A2470-F010-4437-BF68-343D5099C19D</RequestId>
    	<DomainExtensionId>de-bp1k4chwdnhxd</DomainExtensionId>
    	<ListenerPort>443</ListenerPort>
    </SetDomainExtensionAttributeResponseResponse>
    ```

-   JSON格式

    ```
    {
        "RequestId": "CCC710F8-285C-415F-9211-9BD6BF7BB997", 
        "DomainExtensions": {
            "DomainExtension": [
                {
                    "ServerCertificateId": "1231579085529123_164b57543a9_464232488_760347667", 
                    "Domain": "*.example2.com", 
                    "DomainExtensionId": "de-bp1k4chwdnhxd"
                }
            ]
        }
    }
    ```


