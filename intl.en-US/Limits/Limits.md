# Limits {#concept_mfm_mp4_tdb .concept}

Server Load Balancer provides an API to query the default limits of an SLB instance. For more information, see [Query Quota-DescribeSlbQuotas](../../../../../intl.en-US//DescribeSlbQuotas.md#).

|Resource|Default limit|
|:-------|:------------|
|**Limits on SLB instances**|
|Number of SLB instances per account|30|
|Number of times that an ECS instance can be added to SLB instances|50|
|Number of backend servers that can be added to an SLB instance|200|
|Number of listeners that can be added to an SLB instance|50|
|Number of domain /URL based forwarding rules that can be added to a Layer-7 listener|40|
|Number of domain name extensions that an HTTPS listener can create|3|
|Frequency of API calls per an AccessKey|5,000 times/day|
|Frontend/backend port range used by a listener \(public cloud\)|1-65535|
|Frontend/backend port range used by a listener \(Ant Financial Cloud\)|80, 443, 2800-3300, 5000-10000, 13000-14000|
|**Limits on certificates**|
|Number of server certificates that can be uploaded in a region|100|
|Number of CA certificates that can be uploaded in a region|100|
|**Limits on access control lists**|
|Number of access control lists that can be created in a region|50|
|Number of access control entries that can be added to an access control list|300|
|Number of IP entries that can be added to an access control list in an API call|50|
|Number of times that an access control list can be added to listeners|50|

