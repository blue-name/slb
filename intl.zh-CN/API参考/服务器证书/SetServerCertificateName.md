# SetServerCertificateName {#reference_o2z_yz2_ndb .reference}

设置服务器证书名称。

## 调试 {#section_kgz_jb1_rfb .section}

```
点击[这里](https://api.aliyun.com/#product=Slb&api=SetServerCertificateName)在OpenAPI Explorer中可视化调试，并自动生成SDK调用示例。
```

## 请求参数 {#section_bqw_c1g_cz .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|要执行的操作，取值：SetServerCertificateName

|
|ServerCertificateId|String|是|服务器证书ID。|
|RegionId|String|是|负载均衡实例的地域。您可以通过调用 DescribeRegions接口获取地域ID。

|
|ServerCertificateName|String|是|服务器证书名称。长度为1-80个英文或中文字符，必须以大小字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。

|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|说明|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#public}
https://slb.aliyuncs.com/?Action=SetServerCertificateName
&RegionId=cn-hangzhou
&ServerCertificateId=139a00604ad-cn-east-hangzhou-01
&ServerCertificateName=abc
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <SetServerCertificateNameResponse>
    	<RequestId>CEF72CEB-54B6-4AE8-B225-F876FE7BA984</RequestId>
    </SetServerCertificateNameResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId": " CEF72CEB-54B6-4AE8-B225-F876FE7BA984"
    }
    ```


