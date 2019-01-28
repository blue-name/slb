# UploadServerCertificate {#reference_qbv_nw2_ndb .reference}

上传服务器证书。

一次只能上传一份服务器证书和对应的PrivateKey。该接口保证事务性，即上传的证书和PrivateKey要么都上传成功，要么都不成功。上传成功后，返回该用户的所有服务器证书列表的Fingerprint。

## 请求参数 {#section_bqw_c1g_cz .section}
问题:如果不是阿里云的云上证书,哪些参数是必要的,哪些参数是不需要的?

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是|要执行的操作，取值：UploadServerCertificate

|
|RegionId|String|是|服务器证书的。您可以通过调用 DescribeRegions接口获取地域ID。

|
|ServerCertificate|String|否|要上传的安全证书。|
|ServerCertificateName|String|否|要上传的安全证书的名称。|
|PrivateKey|String|是|要上传的私钥。|
|AliCloudCertificateId|String|否|阿里云的云上证书ID。|
|AliCloudCertificateName|String|否|阿里云的云上证书名称。|
|ResourceGroupId|String|否|企业资源组ID。|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|ServerCertificateId|String|服务器证书ID。|
|ServerCertificateName|String|服务器证书名称。|
|Fingerprint|String|服务器证书的指纹。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#public}
https://slb.aliyuncs.com/?Action=UploadServerCertificate
&RegionId=cn-hangzhou-01
&ServerCertificate=test
&ServerCertificateName=mycert01
&PrivateKey=wmsad!q23
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <UploadServerCertificateResponse>
    	<RequestId>365F4154-92F6-4AE4-92F8-7FF34B540710</RequestId>
    	<ServerCertificateId>idkp-123-cn-test-01</ServerCertificateId>
    	<ServerCertificateName>mycert01</ServerCertificateName>
    	<Fingerprint>01:DF:AB:CD</Fingerprint>
    </UploadServerCertificateResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId":"365F4154-92F6-4AE4-92F8-7FF34B540710",
      "ServerCertificateId":"idkp-123-cn-test-01",
      "ServerCertificateName":"mycert01",
      "Fingerprint":"01:DF:AB:CD"
    }
    ```


