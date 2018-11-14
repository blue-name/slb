# Guaranteed-performance instance billing FAQ {#concept_tkd_jh5_vdb .concept}

## 1. When will the guaranteed-performance instance start charging the specification fees? {#section_zqv_zby_wdb .section}

Alibaba Cloud Server Load Balancer \(SLB\) launched the guaranteed-performance instances in May, 2017, and started the testing at the same time. For now, the guaranteed-performance instance has been tested for 10 months. SLB will charge the specification fee on guaranteed-performance instances from April 1, 2018. For more information, see [How to use guaranteed-performance instances?](../../../../reseller.en-US/Miscellaneous/FAQ/How to use guaranteed-performance SLB instances?.md#).

The fee collection for the guaranteed-performance instances take effect in batches by regions:

-   The first batch:

    Effective time: From April 1 to April 10

    Regions: Singapore, Malaysia \(Kuala Lumpur\), Indonesia \(Jakarta\), India \(Mumbai\), US \(Silicon Valley\), US \(Virginia\)

-   The second batch:

    Effective time: From April 11 to April 20

    Effective regions: China \(Hangzhou\), China \(Zhangjiakou\), China \(Hohhot\), China \(Hong Kong\)

-   The third batch:

    Effective time: From April 21 to April 30

    Effective regions: China North 1 \(Qingdao\), China North 2 \(Beijing\), China East 2 \(Shanghai\), China South 1 \(Shenzhen\)


## 2. Will intranet SLB instances be charged for specification fee? {#section_z11_2cy_wdb .section}

-   If the intranet SLB instance is a shared-performance SLB instance, no specification fees are collected.
-   If the intranet SLB instance is a guaranteed-performance SLB instance, corresponding specification fees are collected.

    The specification fees are collected as the same as the Internet guaranteed-performance instances, but intranet guaranteed-performance instances are free from instance fee and traffic fee.


## 3. Will the billing of shared-performance instances be affected after the specification fees are charged? {#section_drv_zby_wdb .section}

No.

The shared-performance instances will not be charged for the specification fee.

However, if you change the shared-performance instances to the guaranteed-performance instances, the specification fees will be collected from April 1, 2018.

## 4. Can shared-performance instances be changed to guaranteed-performance instances? {#section_erv_zby_wdb .section}

Yes.

Once an instance is changed to the guaranteed-performance type, it cannot change back and will be charged from April 1st.

## 5. What are the specifications for shared-performance instances? {#section_frv_zby_wdb .section}

Shared-performance instances do not guarantee the performance. No specifications are available.

## 6. How to select a performance specification? {#section_nmk_fcy_wdb .section}

-   You can select the largest specification for Pay-As-You-Go instances, because Pay-As-You-Go instance are charged according to the actual usage and are free of charge in idle time.

## 7. What are the prices of performance specifications? {#section_irv_zby_wdb .section}

Six specifications are provided for guaranteed-performance SLB instances. No specification fee is collected for the Standard I \(slb.s1.small\) specification. For more information, see [Billing](../../../../reseller.en-US/Miscellaneous/FAQ/How to use guaranteed-performance SLB instances?.md#section_n5z_s1n_vdb).

## 8. Are the traffic fee and instance fee of guaranteed-performance instances the same as those of shared-performance instances? {#section_jrv_zby_wdb .section}

Yes.

## 9. How many guaranteed-performance instances can be created? {#section_krv_zby_wdb .section}

Same as the shared-performance instances, you can purchase up to 60 guaranteed-performance instances. Open a ticket to apply for more quota.

## 10. Can I adjust the specification of a guaranteed-performance instance? {#section_lrv_zby_wdb .section}

Yes.

-   You can upgrade or downgrade a Pay-As-You-Go guaranteed-performance instance. For more information, see [Change the configuration](../../../../reseller.en-US/Archives/User Guide (Old Console)/SLB instances/Change the configuration.md#).

**Note:** 

-   Once a shared-performance instance is changed to a guaranteed-performance instance, it cannot be changed back.
-   Some instances may exist in older clusters due to historical stock. These instances need to be migrated when they are changed to guaranteed-performance instances. Therefore a service interruption of 10-30 seconds may occur. We recommend that you change the instance type when the traffic is low.

## 9. Can I still buy shared-performance instances? {#section_orv_zby_wdb .section}

Yes.

However, the shared-performance instances will be phased out in the future. Please pay attention to the official notifications.

