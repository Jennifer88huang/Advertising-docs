---
title: ProfileCriterion Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a criterion that can be used to show ads to users in a specific company, industry, or job function.
---
> [!IMPORTANT]
> The Bing Ads API Version 13 preview documentation is subject to change. To view version 12 content, use the version selector near the table of contents at the top and left side of the page.

# ProfileCriterion Data Object - Campaign Management
Defines a criterion that can be used to show ads to users in a specific company, industry, or job function.

The *ProfileCriterion* criterion can be included within [AdGroupCriterion](adgroupcriterion.md), [NegativeAdGroupCriterion](negativeadgroupcriterion.md), and [CampaignCriterion](campaigncriterion.md) objects. Bing Ads applies a union of both campaign and ad group level profile criterions. However, if you apply a criterion with the same profile ID e.g., target or exclude the same company name at both the campaign and ad group level, then the ad group level criterion will override the campaign level criterion. 

## Syntax
```xml
<xs:complexType name="ProfileCriterion" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Criterion">
      <xs:sequence>
        <xs:element minOccurs="0" name="ProfileId" type="xs:long" />
        <xs:element minOccurs="0" name="ProfileType" type="tns:ProfileType" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="profileid"></a>ProfileId|The identifier of the audience profile that you want to target.<br/><br/>**Add:** Required<br/>**Update:** Required|**long**|
|<a name="profiletype"></a>ProfileType|Determines whether the profile criterion corresponds to a company name, industry, or job function.<br/><br/>**Add:** Required<br/>**Update:** Required|[ProfileType](profiletype.md)|

The [ProfileCriterion](profilecriterion.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementscriterion"></a>Inherited Elements from Criterion
The [ProfileCriterion](profilecriterion.md) object derives from the [Criterion](criterion.md) object, and inherits the following elements. The descriptions below are specific to [ProfileCriterion](profilecriterion.md), and might not apply to other objects that inherit the same elements from the [Criterion](criterion.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|The type of the criterion. This value is *Profile* when you retrieve a profile criterion. For more information about criterion types, see the [Criterion Data Object Remarks](criterion.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  
