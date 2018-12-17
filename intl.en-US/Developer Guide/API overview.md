# API overview {#concept_qyw_x1d_cz .concept}

## SLB instance {#section_rpm_m2w_pdb .section}

|API|Description|
|:--|:----------|
|[CreateLoadBalancer](intl.en-US/Developer Guide/Server Load Balancer instance/CreateLoadBalancer.md#)|Creates an SLB instance.|
|[ModifyLoadBalancerInternetSpec](intl.en-US/Developer Guide/Server Load Balancer instance/ModifyLoadBalancerInternetSpec.md#)|Modify the billing method or specification of an SLB instance.|
|[DeleteLoadBalancer](intl.en-US/Developer Guide/Server Load Balancer instance/DeleteLoadBalancer.md#)|Delete an SLB instance.|
|[SetLoadBalancerStatus](intl.en-US/Developer Guide/Server Load Balancer instance/SetLoadBalancerStatus.md#)|Set the status of an SLB instance.|
|[SetLoadBalancerName](intl.en-US/Developer Guide/Server Load Balancer instance/SetLoadBalancerName.md#)|Configure the name of an SLB instance.|
|[DescribeLoadBalancers](intl.en-US/Developer Guide/Server Load Balancer instance/DescribeLoadBalancers.md#)|Query created SLB instances.|
|[DescribeLoadBalancerAttribute](intl.en-US/Developer Guide/Server Load Balancer instance/DescribeLoadBalancerAttribute.md#)|Query the detailed information of an SLB instance.|
|[ModifyLoadBalancerInstanceSpec](intl.en-US/Developer Guide/Server Load Balancer instance/ModifyLoadBalancerInstanceSpec.md#)|Modify the specification of an SLB instance.|
|[Describeregions](intl.en-US/Developer Guide/Server Load Balancer instance/Describeregions.md#)|Query regions.|
|[DescribeZones](intl.en-US/Developer Guide/Server Load Balancer instance/DescribeZones.md#)|Query zones in a region.|

## Listener {#section_dc5_gfw_pdb .section}

|API|Description|
|:--|:----------|
|**TCP listener**|
|[CreateLoadBalancerTCPListener](intl.en-US/Developer Guide/TCP listener/CreateLoadBalancerTCPListener.md#)|Create a TCP listener.|
|[SetLoadBalancerTCPListenerAttribute](intl.en-US/Developer Guide/TCP listener/SetLoadBalancerTCPListenerAttribute.md#)|Modify the configurations of a TCP listener.|
|[DescribeLoadBalancerTCPListenerAttribute](intl.en-US/Developer Guide/TCP listener/DescribeLoadBalancerTCPListenerAttribute.md#)|Query the configurations of a TCP listener.|
|**UDP listener**|
|[CreateLoadBalancerUDPListener](intl.en-US/Developer Guide/UDP监听/CreateLoadBalancerUDPListener.md#)|Create a UDP listener.|
|[SetLoadBalancerUDPListenerAttribute](intl.en-US/Developer Guide/UDP监听/SetLoadBalancerUDPListenerAttribute.md#)|Modify the configurations of a UDP listener.|
|[DescribeLoadBalancerUDPListenerAttribute](intl.en-US/Developer Guide/UDP监听/DescribeLoadBalancerUDPListenerAttribute.md#)|Query the configurations of a UDP listener.|
|**HTTP listener**|
|[CreateLoadBalancerHTTPListener](intl.en-US/Developer Guide/HTTP listener/CreateLoadBalancerHTTPListener.md#)|Create an HTTP listener.|
|[SetLoadBalancerHTTPListenerAttribute](intl.en-US/Developer Guide/HTTP listener/SetLoadBalancerHTTPListenerAttribute.md#)|Modify the configurations of an HTTP listener.|
|[DescribeLoadBalancerHTTPListenerAttribute](intl.en-US/Developer Guide/HTTP listener/DescribeLoadBalancerHTTPListenerAttribute.md#)|Query the configurations of an HTTP listener.|
|**HTTPS listener**|
|[CreateLoadBalancerHTTPSListener](intl.en-US/Developer Guide/HTTPS listener/CreateLoadBalancerHTTPSListener.md#)|Create an HTTPS listener.|
|[SetLoadBalancerHTTPSListenerAttribute](intl.en-US/Developer Guide/HTTPS listener/SetLoadBalancerHTTPSListenerAttribute.md#)|Modify the configurations of an HTTPS listener.|
|[DescribeLoadBalancerHTTPSListenerAttribute](intl.en-US/Developer Guide/HTTPS listener/DescribeLoadBalancerHTTPSListenerAttribute.md#)|Query the configurations of an HTTPS listener.|
|[StartLoadBalancerListener](intl.en-US/Developer Guide/Listeners/StartLoadBalancerListener.md#)|Start a listener.|
|[Deleteloadbalancerlistener](intl.en-US/Developer Guide/Listeners/Deleteloadbalancerlistener.md#)|Delete a listener.|
|[StopLoadBalancerListener](intl.en-US/Developer Guide/Listeners/StopLoadBalancerListener.md#)|Stop a listener.|
|**Access control**|
|[SetListenerAccessControlStatus](intl.en-US/Developer Guide/Access control/SetListenerAccessControlStatus.md#)|Enable or disable the access control function of a listener.|
|[DescribeListenerAccessControlAttribute](intl.en-US/Developer Guide/Access control/DescribeListenerAccessControlAttribute.md#)|Query the access control configurations of a listener.|
|[AddListenerWhiteListItem](intl.en-US/Developer Guide/Access control/AddListenerWhiteListItem.md#)|Add a whitelist to a listener.|
|[RemoveListenerWhiteListItem](intl.en-US/Developer Guide/Access control/RemoveListenerWhiteListItem.md#)|Delete an IP address from the whitelist of a listener.|
|**Forwarding rule**|
|[CreateRules](intl.en-US/Developer Guide/Forwarding rules/CreateRules.md#)|Add forwarding rules to an HTTP/HTTPS listener.|
|[DeleteRules](intl.en-US/Developer Guide/Forwarding rules/DeleteRules.md#)|Delete forwarding rules.|
|[SetRule](intl.en-US/Developer Guide/Forwarding rules/SetRule.md#)|Change the target VServer group of a forwarding rule.|
|[DescribeRules](intl.en-US/Developer Guide/Forwarding rules/DescribeRules.md#)|Query the forwarding rules associated with a listener.|
|[DescribeRuleAttribute](intl.en-US/Developer Guide/Forwarding rules/DescribeRuleAttribute.md#)|Query the detailed configurations of a forwarding rule.|
|**Domain name extension \(Beta\)**|
|[CreateDomainExtension](intl.en-US/Developer Guide/Domain name extension (Beta)/CreateDomainExtension.md#)|Create a domain name extension.|
|[SetDomainExtensionAttribute](intl.en-US/Developer Guide/Domain name extension (Beta)/SetDomainExtensionAttribute.md#)|Configure an added domain name extension.|
|[DescribeDomainExtensions](intl.en-US/Developer Guide/Domain name extension (Beta)/DescribeDomainExtensions.md#)|Query added domain name extensions.|
|[DeleteDomainExtension](intl.en-US/Developer Guide/Domain name extension (Beta)/DeleteDomainExtension.md#)|Delete an added domain name extension.|

## Backend server {#section_vpc_kff_cz .section}

|API|Description|
|:--|:----------|
|**Default server group**|
|[AddBackendServers](intl.en-US/Developer Guide/Backend server/AddBackendServers.md#)|Add default servers.|
|[RemoveBackendServers](intl.en-US/Developer Guide/Backend server/RemoveBackendServers.md#)|Remove default servers.|
|[SetBackendServers](intl.en-US/Developer Guide/Backend server/SetBackendServers.md#)|Configure the weights of default servers.|
|[DescribeHealthStatus](intl.en-US/Developer Guide/Backend server/DescribeHealthStatus.md#)|Perform health check on the default servers of an SLB instance, and the health status of the default servers is returned.|
|**VServer group**|
|[CreateVServerGroup](intl.en-US/Developer Guide/VServer groups/CreateVServerGroup.md#)|Create a VServer group and add backend servers to the VServer group.|
|[SetVServerGroupAttribute](intl.en-US/Developer Guide/VServer groups/SetVServerGroupAttribute.md#)|Modify the configurations of a VServer group.|
|[AddVServerGroupBackendServers](intl.en-US/Developer Guide/VServer groups/AddVServerGroupBackendServers.md#)|Add backend servers to a VServer group.|
|[RemoveVServerGroupBackendServers](intl.en-US/Developer Guide/VServer groups/RemoveVServerGroupBackendServers.md#)|Remove backend servers from a VServer group.|
|[ModifyVServerGroupBackendServers](intl.en-US/Developer Guide/VServer groups/ModifyVServerGroupBackendServers.md#)|Replace backend servers in a VServer group.|
|[DeleteVServerGroup](intl.en-US/Developer Guide/VServer groups/DeleteVServerGroup.md#)|Delete a VServer group.|
|[DescribeVServerGroups](intl.en-US/Developer Guide/VServer groups/DescribeVServerGroups.md#)|Query created VServer groups.|
|[DescribeVServerGroupAttribute](intl.en-US/Developer Guide/VServer groups/DescribeVServerGroupAttribute.md#)|Query the detailed information of a VServer group.|
|**Active/standby server group**|
|[CreateMasterSlaveServerGroup](intl.en-US/Developer Guide/Master-slave server group/CreateMasterSlaveServerGroup.md#)|Create an active/standby server group.|
|[DeleteMasterSlaveServerGroup](intl.en-US/Developer Guide/Master-slave server group/DeleteMasterSlaveServerGroup.md#)|Delete an active/standby server group.|
|[DescribeMasterSlaveServerGroupAttribute](intl.en-US/Developer Guide/Master-slave server group/DescribeMasterSlaveServerGroupAttribute.md#)|Query the detailed information of an active/standby server group.|
|[DescribeMasterSlaveServerGroups](intl.en-US/Developer Guide/Master-slave server group/DescribeMasterSlaveServerGroups.md#)|Query created active/standby server groups.|

## Access control {#section_evr_pcy_5db .section}

|API|Description|
|:--|:----------|
|[CreateAccessControlList](intl.en-US/Developer Guide/Access control/CreateAccessControlList.md#)|Create an access control list.|
|[DeleteAccessControlList](intl.en-US/Developer Guide/Access control/DeleteAccessControlList.md#)|Delete an access control list.|
|[DescribeAccessControlLists](intl.en-US/Developer Guide/Access control/DescribeAccessControlLists.md#)|Query created access control lists.|
|[DescribeAccessControlListAttribute](intl.en-US/Developer Guide/Access control/DescribeAccessControlListAttribute.md#)|Query the configurations of an access control list.|
|[SetAccessControlListAttribute](intl.en-US/Developer Guide/Access control/SetAccessControlListAttribute.md#)|Modify the name of an access control list.|
|[AddAccessControlListEntry](intl.en-US/Developer Guide/Access control/AddAccessControlListEntry.md#)|Add an IP entry to the access control list.|
|[RemoveAccessControlListEntry](intl.en-US/Developer Guide/Access control/RemoveAccessControlListEntry.md#)|Delete an IP entry from the access control list.|

## Tag {#section_w4z_lff_cz .section}

|API|Description|
|:--|:----------|
|[AddTags](intl.en-US/Developer Guide/Tag/AddTags.md#)|Add tags to an SLB instance.|
|[DescribeTags](intl.en-US/Developer Guide/Tag/DescribeTags.md#)|Query created tags.|
|[RemoveTags](intl.en-US/Developer Guide/Tag/RemoveTags.md#)|Unbind tags from an SLB instance.|

## Server certificate {#section_wpm_bvp_y2b .section}

|API|Description|
|---|-----------|
|[UploadServerCertificate](intl.en-US/Developer Guide/Server certificate/UploadServerCertificate.md#)|Upload a server certificate.|
|[DeleteServerCertificate](intl.en-US/Developer Guide/Server certificate/DeleteServerCertificate.md#)|Delete a server certificate.|
|[DescribeServerCertificates](intl.en-US/Developer Guide/Server certificate/DescribeServerCertificates.md#)|Query uploaded server certificates in a region.|
|[SetServerCertificateName](intl.en-US/Developer Guide/Server certificate/SetServerCertificateName.md#)|Configure a name for a server certificate.|
|[UploadCACertificate](intl.en-US/Developer Guide/Server certificate/UploadCACertificate.md#)|Upload the CA certificate.|
|[DeleteCACertificate](intl.en-US/Developer Guide/Server certificate/DeleteCACertificate.md#)|Delete a CA certificate.|
|[DescribeCACertificates](intl.en-US/Developer Guide/Server certificate/DescribeCACertificates.md#)|Query the uploaded CA certificates.|
|[SetCACertificateName](intl.en-US/Developer Guide/Server certificate/SetCACertificateName.md#)|Configure a name for a CA certificate.|

## Query resource limits {#section_vws_rvp_y2b .section}

|API|Description|
|---|-----------|
|[Query Quota-DescribeSlbQuotas](intl.en-US//DescribeSlbQuotas.md#)|Query the resource limits of Server Load Balancer.|

