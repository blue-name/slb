# Multiple-zone deployment {#concept_i55_h4n_vdb .concept}

You can create SLB instances in a region with multiple zones to improve the availability.

## What is multiple-zone deployment? {#section_blw_bxt_vdb .section}

A cloud product zone refers to a set of independent infrastructures. Different zones have independent infrastructures \(such as network, power supply and air-conditioning\), thus an infrastructure fault in one zone does not affect other zones.

To provide more reliable services, SLB has deployed multiple zones in most regions to achieve disaster recovery across data centers. When the data center in the primary zone is faulty and unavailable, SLB is able to switch to the data center in the backup zone to restore its service capabilities within 30 seconds.

Note the following about SLB primary/backup zones:

-   SLB supports attaching ECS instances in different zones as long as the ECS instances and the SLB instance are in the same region. SLB can distribute traffic to the ECS instances in different zones.
-   Normally, the SLB instance in the backup zone is in the backup state. You cannot manually switch the primary/backup state of an SLB instance. SLB switches to the backup zone only when the whole primary zone is unavailable due to data center outage or exit cable failure and more. SLB will not switch to the backup zone if only one instance in the primary zone is faulty.
-   SLB and ECS are deployed in different clusters. When an SLB instance in Zone A is unavailable, the ECS instances in Zone A are not necessarily unavailable. Therefore, after SLB switches to the backup zone, the SLB instance in the backup zone still can distribute traffic to the added ECS instances. However, if all clusters in a zone is unavailable or the optical cable is faulty, all services \(including but not limited to SLB instances and ECS instances\) in the zone cannot work anymore.

For more information, see [SLB high availability](../reseller.en-US/Miscellaneous/Best practices/High availability best practice.md#).

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/4155/15421815092835_en-US.png)

## Primary/backup zone list {#section_ml2_ykb_wdb .section}

The following table lists the primary/backup zones in different regions. You can call the DescribeZones API to obtain available primary/backup zones in a region.

|Region|Zone type|Zones|
|:-----|:--------|:----|
|China \(Hangzhou\)|Multi-zone|**Primary zone**|**Backup zone**|
|Zone B|Zone D|
|Zone D|Zone E|
|Zone E|Zone F|
|Zone F|Zone E|
|China \(Shanghai\)|Multi-zone|**Primary zone**|**Backup zone**|
|Zone A|Zone B|
|Zone B|Zone A or Zone D|
|Zone C|Zone B|
|Zone D|Zone B|
|China \(Shenzhen\)|Multi-zone|**Primary zone**|**Backup zone**|
|Zone A|Zone B|
|Zone B|Zone A|
|Zone C|Zone B|
|China \(Qingdao\)|Multi-zone|**Primary zone**|**Backup zone**|
|Zone B|Zone C|
|Zone C|Zone B|
|China \(Beijing\)|Multi-zone|**Primary zone**|**Backup zone**|
|Zone A|Zone B or Zone D|
|Zone B|Zone A or Zone C|
|Zone C|Zone B|
|Zone D|Zone A|
|China \(Zhangjiakou\)|Single-zone|Zone A|Zone A|
|China \(Hohhot\)|Single-zone|Zone A|Zone A|
|Germany \(Frankfurt\)|Singe-zone|Zone A|Zone A|
|UAE \(Dubai\)|Single-zone|Zone A|Zone A|
|Singapore|Multi-zone|**Primary zone**|**Backup zone**|
|Zone A|Zone B|
|Zone B|Zone A|
|Australia \(Sydney\)|Single-zone|Zone A|Zone A|
|Malaysia \(Kuala Lumpur\)|Single-zone|Zone A|Zone A|
|Japan \(Tokyo\)|Single-zone|Zone A|Zone A|
|China \(Hong Kong\)|Multi-zone|**Primary zone**|**Backup zone**|
|Zone B|Zone C|
|Zone C|Zone B|
|US \(Virginia\)|Single-zone|Zone A|Zone A|
|US \(Silicon Valley\)|Multi-zone|**Primary zone**|**Backup zone**|
|Zone A|Zone B|
|Zone B|Zone A|

