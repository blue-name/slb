# CreateLoadBalancerHTTPSListener {#slb_api_CreateLoadBalancerHTTPSListener .reference}

创建HTTPS监听。

**说明：** 新建的监听的状态为stopped。创建完成后，需调用StartLoadBalancerListener接口启动监听进行流量转发。

## 调试 {#section_pl4_vsz_qfb .section}

```
点击[这里](https://api.aliyun.com/#product=Slb&api=CreateLoadBalancerHTTPSListener)在OpenAPI Explorer中可视化调试，并自动生成SDK调用示例。
```

## 请求参数 {#section_bqw_c1g_cz .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|要执行的操作。取值：CreateLoadBalancerHTTPSListener

|
|RegionId|String|是|负载均衡实例的地域。您可以通过调用 DescribeRegions接口获取地域ID。

|
|LoadBalancerId|String|是|负载均衡实例ID。|
|ListenerPort|Integer|是|负载均衡实例前端使用的端口，取值：1-65535

|
|BackendServerPort|Integer|是|负载均衡实例后端使用的端口。取值：1-65535

**说明：** 如果不使用服务器组（不指定VServerGroupId参数），则该参数必选。

|
|VServerGroupId|String|否|服务器组ID。|
|ServerCertificateId|String|是|服务器证书的ID。|
|CACertificateId|String|否|CA证书ID。若既上传CA证书又上传服务器证书，即采用双向认证；若用户只上传服务器证书，即为单向认证。

|
|Bandwidth|Integer|是|监听的带宽峰值，取值：-   -1：不限制带宽峰值。
-   \[1-5000\]：监听的带宽峰值，所有监听的带宽峰值之和不能超过实例的带宽峰值。

|
|Scheduler|String|否|调度算法。取值：-   wrr（默认值）：权重值越高的后端服务器，被轮询到的次数（概率）也越高。
-   wlc：除了根据每台后端服务器设定的权重值来进行轮询，同时还考虑后端服务器的实际负载（即连接数）。当权重值相同时，当前连接数越小的后端服务器被轮询到的次数（概率）也越高。
-   rr：按照访问顺序依次将外部请求依序分发到后端服务器。

|
|StickySession|String|是|是否开启会话保持，取值：on | off

|
|StickySessionType|String|否|cookie的处理方式。取值：-   insert：植入Cookie。

客户端第一次访问时，负载均衡会在返回请求中植入Cookie（即在HTTP/HTTPS响应报文中插入SERVERID），下次客户端携带此Cookie访问，负载均衡服务会将请求定向转发给之前记录到的后端服务器上。

-   server：重写Cookie。

负载均衡发现用户自定义了Cookie，将会对原来的Cookie进行重写，下次客户端携带新的Cookie访问，负载均衡服务会将请求定向转发给之前记录到的后端服务器。

**说明：** 当StickySession的值为on时，必须指定该参数。


|
|CookieTimeout|Integer|否|Cookie超时时间。取值： 1-86400（秒）

**说明：** 当StickySession为on且StickySessionType为insert时，该参数必选。

|
|Cookie|String|否|服务器上配置的Cookie。长度为1-200个字符，只能包含ASCII英文字母和数字字符，不能包含逗号、分号或空格，也不能以$开头。

当StickySession为on且StickySessionType为server时，该参数必选。

|
|IdleTimeout|String|否|指定连接空闲超时时间，取值范围为1-60秒，默认值为15秒。在超时时间内一直没有访问请求，负载均衡会暂时中断当前连接，直到一下次请求来临时重新建立新的连接。

|
|RequestTimeout|String|否|指定请求超时时间，取值范围为1-180秒，默认值为60秒。在超时时间内后端服务器一直没有响应，负载均衡将放弃等待，给客户端返回HTTP 504错误码。

|
|AclStatus|String|否|是否开启访问控制功能。取值：on | off（默认值）

|
|AclType|String|否|访问控制类型：-   white： 仅转发来自所选访问控制策略组中设置的IP地址或地址段的请求，白名单适用于应用只允许特定IP访问的场景。

设置白名单存在一定业务风险。一旦设置白名单，就只有白名单中的IP可以访问负载均衡监听。如果开启了白名单访问，但访问策略组中没有添加任何IP，则负载均衡监听会转发全部请求。

-   black： 来自所选访问控制策略组中设置的IP地址或地址段的所有请求都不会转发，黑名单适用于应用只限制某些特定IP访问的场景。

如果开启了黑名单访问，但访问策略组中没有添加任何IP，则负载均衡监听会转发全部请求。


当AclStatus参数的值为on时，该参数必选。

|
|AclId|String|否|监听绑定的访问策略组ID。当AclStatus参数的值为on时，该参数必选。

|
|Description|String|否|设置监听的描述信息。|
|HealthCheck|String|是|是否开启健康检查。取值：on | off

|
|HealthCheckDomain|String|否|用于健康检查的域名，取值：-   $\_ip： 后端服务器的私网IP。当指定了IP或该参数未指定时，负载均衡会使用各后端服务器的私网IP当做健康检查使用的域名。
-   domain：域名长度为1-80字符，只能包含字母、数字、点号（.）和连字符（-）。

|
|HealthCheckURI|String|否|用于健康检查的URI。|
|HealthCheckConnectPort|Integer|否|健康检查使用的端口。取值：-   1-65535：健康检查的后端服务器的端口。

**说明：** 若不指定，默认使用监听配置


|
|HealthyThreshold|Integer|否|健康检查连续成功多少次后，将后端服务器的健康检查状态由fail判定为success。取值：2-10

|
|UnhealthyThreshold|Integer|否|健康检查连续失败多少次后，将后端服务器的健康检查状态由success判定为fail。取值：2-10

|
|HealthCheckTimeout|Integer|否|接收来自运行状况检查的响应需要等待的时间。如果后端ECS在指定的时间内没有正确响应，则判定为健康检查失败。取值：1-300（秒）

**说明：** 如果HealthCHeckTimeout的值小于HealthCheckInterval的值，则HealthCHeckTimeout无效，超时时间为HealthCheckInterval的值。

|
|HealthCheckInterval|Integer|否|健康检查的时间间隔。取值：1-50（秒）

|
|HealthCheckHttpCode|String|否|健康检查正常的HTTP状态码，多个状态码用逗号分隔。取值：http\_2xx（默认值） | http\_3xx | http\_4xx | http\_5xx

|
|Gzip|String|否|是否开启Gzip压缩，对特定文件类型进行压缩。取值：on（默认值）| off

|
|TLSCipherPolicy|String|否| 只有性能保障型实例才可以指定TLSCipherPolicy参数，每种policy定义了一种安全策略，安全策略包含HTTPS可选的TLS协议版本和配套的加密算法套件。

 目前支持以下四种安全策略，详细区别请参见[TLS安全策略差异说明](#section_ulc_g3q_32b)，请根据实际情况选择对应的policy。

 -   tls\_cipher\_policy\_1\_0：
    -   支持TLS版本： TLSv1.0、TLSv1.1和TLSv1.2。
    -   支持加密算法套件：ECDHE-RSA-AES128-GCM-SHA256、ECDHE-RSA-AES256-GCM-SHA384、ECDHE-RSA-AES128-SHA256、ECDHE-RSA-AES256-SHA384、AES128-GCM-SHA256、AES256-GCM-SHA384、AES128-SHA256、AES256-SHA256、ECDHE-RSA-AES128-SHA、ECDHE-RSA-AES256-SHA、AES128-SHA、AES256-SHA和DES-CBC3-SHA。
-   tls\_cipher\_policy\_1\_1：
    -   支持TLS版本： TLSv1.1和TLSv1.2。
    -   支持加密算法套件：ECDHE-RSA-AES128-GCM-SHA256、ECDHE-RSA-AES256-GCM-SHA384、ECDHE-RSA-AES128-SHA256、ECDHE-RSA-AES256-SHA384、AES128-GCM-SHA256、AES256-GCM-SHA384、AES128-SHA256、AES256-SHA256、ECDHE-RSA-AES128-SHA、ECDHE-RSA-AES256-SHA、AES128-SHA、AES256-SHA和DES-CBC3-SHA。
-   tls\_cipher\_policy\_1\_2
    -   支持TLS版本：TLSv1.2。
    -   支持加密算法套件：ECDHE-RSA-AES128-GCM-SHA256、ECDHE-RSA-AES256-GCM-SHA384、ECDHE-RSA-AES128-SHA256、ECDHE-RSA-AES256-SHA384、AES128-GCM-SHA256、AES256-GCM-SHA384、AES128-SHA256、AES256-SHA256、ECDHE-RSA-AES128-SHA、ECDHE-RSA-AES256-SHA、AES128-SHA、AES256-SHA和DES-CBC3-SHA。
-   tls\_cipher\_policy\_1\_2\_strict
    -   支持TLS版本：TLSv1.2。
    -   支持加密算法套件：ECDHE-RSA-AES128-GCM-SHA256、ECDHE-RSA-AES256-GCM-SHA384、ECDHE-RSA-AES128-SHA256、ECDHE-RSA-AES256-SHA384、ECDHE-RSA-AES128-SHA和ECDHE-RSA-AES256-SHA。

 |
|EnableHttp2|String|否|是否开启HTTP/2特性。取值：on（默认值）|off

|

## TLS安全策略差异说明 {#section_ulc_g3q_32b .section}

|policy|tls\_cipher\_policy\_1\_0|tls\_cipher\_policy\_1\_1|tls\_cipher\_policy\_1\_2|tls\_cipher\_policy\_1\_2\_strict|
|------|-------------------------|-------------------------|-------------------------|---------------------------------|
|TLS| |1.2/1.1/1.0|1.2/1.1|1.2|1.2|
|CIPHER|ECDHE-RSA-AES128-GCM-SHA256|✔|✔|✔|✔|
|ECDHE-RSA-AES256-GCM-SHA384|✔|✔|✔|✔|
|ECDHE-RSA-AES128-SHA256|✔|✔|✔|✔|
|ECDHE-RSA-AES256-SHA384|✔|✔|✔|✔|
|AES128-GCM-SHA256|✔|✔|✔| |
|AES256-GCM-SHA384|✔|✔|✔| |
|AES128-SHA256|✔|✔|✔| |
|AES256-SHA256|✔|✔|✔| |
|ECDHE-RSA-AES128-SHA|✔|✔|✔|✔|
|ECDHE-RSA-AES256-SHA|✔|✔|✔|✔|
|AES128-SHA|✔|✔|✔| |
|AES256-SHA|✔|✔|✔| |
|DES-CBC3-SHA|✔|✔|✔| |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|说明|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#public}
https://slb.aliyuncs.com/
&Action=CreateLoadBalancerHTTPSListener
&LoadBalancerId=lb-t4nj5vuz8ish9emfk1f20
&ListenerPort=443
&BackendServerPort=80
&ServerCertificateId=1231579085529123_15dbf6ff26f_1991415478_2054196746
&Bandwidth=-1
&HealthCheck=on
&HealthCheckDomain=$_ip
&HealthCheckURI=/test/index.html
&HealthCheckConnectPort=8080
&HealthyThreshold=4
&UnhealthyThreshold=4
&HealthCheckTimeout=3
&HealthCheckInterval=5
&VServerGroupId=rsp-cige6j5e7p
&TLSCipherPolicy=tls_cipher_policy_1_0
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <CreateLoadBalancerHTTPSListenerResponse>
    	<RequestId>CEF72CEB-54B6-4AE8-B225-F876FF7BA984</RequestId>
    </CreateLoadBalancerHTTPSListenerResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId": " CEF72CEB-54B6-4AE8-B225-F876FF7BA984"
    }
    ```


