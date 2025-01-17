---
title: Other threat protections from Microsoft Defender for Cloud
description: Learn about the threat protections available from Microsoft Defender for Cloud
ms.topic: overview
ms.date: 05/22/2023
---

# Other threat protections in Microsoft Defender for Cloud

In addition to its built-in [advanced protection plans](defender-for-cloud-introduction.md), Microsoft Defender for Cloud also offers the following threat protection capabilities.

> [!TIP]
> To enable Defender for Cloud's threat protection capabilities, you must enable enhanced security features on the subscription containing the applicable workloads.

<a name="network-layer"></a>

## Threat protection for Azure network layer

Defenders for Cloud network-layer analytics are based on sample [IPFIX data](https://en.wikipedia.org/wiki/IP_Flow_Information_Export), which are packet headers collected by Azure core routers. Based on this data feed, Defender for Cloud uses machine learning models to identify and flag malicious traffic activities. Defender for Cloud also uses the Microsoft Threat Intelligence database to enrich IP addresses.

Some network configurations restrict Defender for Cloud from generating alerts on suspicious network activity. For Defender for Cloud to generate network alerts, ensure that:

- Your virtual machine has a public IP address (or is on a load balancer with a public IP address).
- Your virtual machine's network egress traffic isn't blocked by an external IDS solution.

For a list of the Azure network layer alerts, see the [Reference table of alerts](alerts-reference.md#alerts-azurenetlayer).

<a name="alerts-other"></a>

## Stream security alerts from other Microsoft services

<a name="azure-waf"></a>

### Display Azure WAF alerts in Defender for Cloud

Azure Application Gateway offers a web application firewall (WAF) that provides centralized protection of your web applications from common exploits and vulnerabilities.

Web applications are increasingly targeted by malicious attacks that exploit commonly known vulnerabilities. The Application Gateway WAF is based on Core Rule Set 3.0 or 2.2.9 from the Open Web Application Security Project. The WAF is updated automatically to protect against new vulnerabilities. 

If you have created [WAF Security solution](partner-integration.md#add-data-sources), your WAF alerts are streamed to Defender for Cloud with no other configurations. For more information on the alerts generated by WAF, see [Web application firewall CRS rule groups and rules](../web-application-firewall/ag/application-gateway-crs-rulegroups-rules.md?tabs=owasp31#crs911-31).

> [!NOTE]
> Only WAF v1 is supported and will work with Microsoft Defender for Cloud.

To deploy Azure's Application Gateway WAF, do the following:

1. From the Azure portal, open **Defender for Cloud**.

1. From Defender for Cloud's menu, select **Security solutions**.

1. In the **Add data sources** section, select **Add** for Azure's Application Gateway WAF.

    :::image type="content" source="media/other-threat-protections/deploy-azure-waf.png" alt-text="Screenshot showing where to select add to deploy WAF." lightbox="media/other-threat-protections/deploy-azure-waf.png"::: 


<a name="azure-ddos"></a>

### Display Azure DDoS Protection alerts in Defender for Cloud

Distributed denial of service (DDoS) attacks are known to be easy to execute. They've become a great security concern, particularly if you're moving your applications to the cloud. A DDoS attack attempts to exhaust an application's resources, making the application unavailable to legitimate users. DDoS attacks can target any endpoint that can be reached through the internet.

To defend against DDoS attacks, purchase a license for Azure DDoS Protection and ensure you're following application design best practices. DDoS Protection provides different service tiers. For more information, see [Azure DDoS Protection overview](../ddos-protection/ddos-protection-overview.md).

If you have Azure DDoS Protection enabled, your DDoS alerts are streamed to Defender for Cloud with no other configuration needed. For more information on the alerts generated by DDoS Protection, see [Reference table of alerts](alerts-reference.md#alerts-azureddos).

## Entra Permission Management (formerly Cloudknox)

[Microsoft Entra Permissions Management](../active-directory/cloud-infrastructure-entitlement-management/index.yml) is a cloud infrastructure entitlement management (CIEM) solution. Entra Permission Management provides comprehensive visibility and control over permissions for any identity and any resource in Azure, AWS, and GCP. 
 
As part of the integration, each onboarded Azure subscription, AWS account, and GCP project give you a view of your [Permission Creep Index (PCI)](../active-directory/cloud-infrastructure-entitlement-management/ui-dashboard.md). The PCI is an aggregated metric that periodically evaluates the level of risk associated with the number of unused or excessive permissions across identities and resources. PCI measures how risky identities can potentially be, based on the permissions available to them.

:::image type="content" source="media/other-threat-protections/permission-creep-index.png" alt-text="Screenshot of the three associated permission creed index recommendations for Azure, AWS and GCP." lightbox="media/other-threat-protections/permission-creep-index.png":::

## Next steps
To learn more about the security alerts from these threat protection features, see the following articles:

- [Reference table for all Defender for Cloud alerts](alerts-reference.md)
- [Security alerts in Defender for Cloud](alerts-overview.md)
- [Manage and respond to security alerts in Defender for Cloud](managing-and-responding-alerts.md)
- [Continuously export Defender for Cloud data](continuous-export.md)
