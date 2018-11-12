# Support TLS security policy {#concept_pvl_f1v_cfb .concept}

Guaranteed-performance instances support selecting the TLS security policy to use when you create or configure an HTTP listener.

You can select the TLS security policy when you set advanced configurations of **Protocol and Listener** during adding or configuring an HTTPS listener. For more information, see [Add an HTTPS listener](reseller.en-US/User Guide/Listeners/Add an HTTPS listener.md#).

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21323/154199272111859_en-US.png)

The TLS security policy contains available TLS protocol versions and supporting encryption algorithm suites.

## TLS security policy {#section_vzd_jdv_cfb .section}

|Security policy|Features|Supported TLS versions|Supported encryption algorithm suites|
|---------------|--------|----------------------|-------------------------------------|
|tls\_cipher\_policy\_1\_|Best compatibility and low security|TLSv1.0, TLSv1.1, and TLSv1.2|Supported encryption algorithm suites: ECDHE-RSA-AES128-GCM-SHA256, ECDHE-RSA-AES256-GCM-SHA384, ECDHE-RSA-AES128-SHA256, ECDHE-RSA-AES256-SHA384, AES128-GCM-SHA256, AES256-GCM-SHA384, AES128-SHA256, AES256-SHA256, ECDHE-RSA-AES128-SHA, ECDHE-RSA-AES256-SHA, AES128-SHA, AES256-SHA and DES-CBC3-SHA.|
|tls\_cipher\_policy\_1\_1|Good compatibility and security|TLSv1.1 and TLSv1.2|ECDHE-RSA-AES128-GCM-SHA256, ECDHE-RSA-AES256-GCM-SHA384, ECDHE-RSA-AES128-SHA256, ECDHE-RSA-AES256-SHA384, AES128-GCM-SHA256, AES256-GCM-SHA384, AES128-SHA256, AES256-SHA256, ECDHE-RSA-AES128-SHA, ECDHE-RSA-AES256-SHA, AES128-SHA, AES256-SHA and DES-CBC3-SHA.|
|tls\_cipher\_policy\_1\_2|Good compatibility and high security|Tlsv1.2|ECDHE-RSA-AES128-GCM-SHA256, ECDHE-RSA-AES256-GCM-SHA384, ECDHE-RSA-AES128-SHA256, ECDHE-RSA-AES256-SHA384, AES128-GCM-SHA256, AES256-GCM-SHA384, AES128-SHA256, AES256-SHA256, ECDHE-RSA-AES128-SHA, ECDHE-RSA-AES256-SHA, AES128-SHA, AES256-SHA and DES-CBC3-SHA.|
|tls\_cipher\_policy\_1\_2\_strict|Only support forward security, extremely high security|TLSv1.2|ECDHE-RSA-AES128-GCM-SHA256, ECDHE-RSA-AES256-GCM-SHA384, ECDHE-RSA-AES128-SHA256, ECDHE-RSA-AES256-SHA384, ECDHE-RSA-AES128-SHA and ECDHE-RSA-AES256-SHA.|

## Differences along TLS security policies {#section_dls_q2v_cfb .section}

|Security policy|tls\_cipher\_policy\_1\_0|tls\_cipher\_policy\_1\_1|tls\_cipher\_policy\_1\_2|tls\_cipher\_policy\_1\_2\_strict|
|---------------|-------------------------|-------------------------|-------------------------|---------------------------------|
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

