---
title: Managing Capacity
description: Use the Business Central administration center to manage the storage capacity for a tenant. 
author: jswymer
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: administration, tenant, admin, environment, sandbox, storage, capacity, quota, limit, database size
ms.date: 03/08/2022
ms.author: jswymer
---

# Managing Capacity

To help our customers manage and plan their storage costs on an ongoing basis, the [!INCLUDE[prodadmincenter](../developer/includes/prodadmincenter.md)] includes the **Capacity** page. The **Capacity** page provides an overview of the total database storage usage, with details about the storage used by every environment. The page also displays the currently used and the maximum allowed number of production and sandbox environments available for the customer.  

[!INCLUDE [db-storage-limit](../includes/db-storage-limit.md)]

[!INCLUDE [db-storage-addons](../includes/db-storage-addons.md)]

## Number of environments

[!INCLUDE[prod_short](../developer/includes/prod_short.md)] administrators can create multiple sandbox and production type environments for various purposes, like:

- Creating more business branches
- Moving into more countries
- Expanding within their current country/region
- Development
- Testing changes
- Learning new product capabilities

Every [!INCLUDE[prod_short](../developer/includes/prod_short.md)] customer with [!INCLUDE[prod_short](../developer/includes/prod_short.md)] Premium or Essential subscriptions can use one production environment and three sandbox environments, at no extra charge.  

Customers can also choose to purchase any number of additional production environments via their CSP partner. Each additionally purchased production environment comes with three additional sandbox environments.  

Production and sandbox environments can be created and used in any country/region where [!INCLUDE[prod_short](../developer/includes/prod_short.md)] service is available, also in the country/region where the default [!INCLUDE[prod_short](../developer/includes/prod_short.md)] environments are located. Additional environments can be created by customers, administrators, and partners by using the [!INCLUDE[prodadmincenter](../developer/includes/prodadmincenter.md)].

When customer administrators create users in Microsoft 365 Admin Center and assign them [!INCLUDE[prod_short](../developer/includes/prod_short.md)] licenses, each user, by default, gets access to all [!INCLUDE[prod_short](../developer/includes/prod_short.md)] environments (sandbox and production) under the same single [!INCLUDE[prod_short](../developer/includes/prod_short.md)] license, still acting within the scope of their license within each of these environments. Administrators can limit users' access to any particular environment by [changing their permissions](/dynamics365/business-central/ui-define-granular-permissions), or by [removing users' access](/dynamics365/business-central/ui-how-users-permissions#to-remove-a-users-access-to-the-system) within that environment.

### Customers with Premium or Essentials subscriptions purchased before October 1 2020

Existing customers with [!INCLUDE[prod_short](../developer/includes/prod_short.md)] Premium or Essentials subscriptions purchased before October 1 2020 will keep their existing environment entitlements (three production and three sandbox environments) for one year, until October 1 2021 or until their subscription is renewed or ended, whichever occurs last. 

Access to two additional production environments during this period won't increase your overall database storage capacity and won't enable extra sandbox environments. These benefits are only activated with the production environments purchased by the customers separately.

Examples:

- Your [!INCLUDE[prod_short](../developer/includes/prod_short.md)] subscription renews **before** October 1 2021

    You can use up to three production environments until October 1 2021. After that date, you'll only be entitled to one production and three sandbox environments.

- Your [!INCLUDE[prod_short](../developer/includes/prod_short.md)] subscription renews **after** October 1 2021

    You can use up to three production environments until the day your subscription renews. After that date, you'll only be entitled to one production and three sandbox environments.

When your entitlement for two additional production environments expires, the additional production environments you may have created during that period will still be fully available. You won't be automatically charged for the extra environments. But to become compliant, you'll have to purchase additional production environments via your CSP partner within 30 days following the expiration date. For more information, see the **Exceeding capacity quotas** section. 

Use the **Capacity** page to see how many environments of each type you have available for your organization.  

## Storage

Storage capacity usage of [!INCLUDE[prod_short](../developer/includes/prod_short.md)] is represented by **Database** on the **Capacity** page.  

[!INCLUDE [db-storage-limit](../includes/db-storage-limit.md)]

[!INCLUDE [admin-env-quota](../developer/includes/admin-env-quota.md)]

Apart from the default storage capacity, the customer is entitled to additional storage capacity based on the number of [!INCLUDE[prod_short](../developer/includes/prod_short.md)] licenses they own:  

|License type|Additional storage (for each license of this type)|
|------|-----------|
|Premium| 3 GB|
|Essential| 2 GB|
|Device|1 GB|

[!INCLUDE [db-storage-addons](../includes/db-storage-addons.md)]

The **Storage capacity, by source** section shows how much capacity is available by default, how much extra capacity is added with user licenses, and how much additional capacity was specifically purchased via CSP.  

> [!NOTE]
> Since July 1, 2021, along with introduction of lower-priced capacity add-ons and per-license capacity quota extensions, the capacity occupied by the files or Blob data stored in the [!INCLUDE[prod_short](../developer/includes/prod_short.md)] database (the content of the Tenant Media and Tenant Media Thumbnails tables) is counted towards the overall database storage capacity of the customer (tenant).  

### Storage usage by environment

The **Storage usage by environment** section of the **Capacity** page provides a tenant-level view of where your organization is using storage capacity. Here you can see how much database storage is used by each environment. For each of your environments, you can also navigate to the [Table Information page](/dynamics365/business-central/admin-view-table-information) within [!INCLUDE[prod_short](../developer/includes/prod_short.md)], which let's you see the distribution of data size across tables.

The content of all non-system tables is counted towards the **Database usage** storage. 

> [!IMPORTANT]
> When you uninstall extensions, you have a choice of deleting or leaving the extension data in the database. If you decide not to delete the data when uninstalling extensions, this data will be counted in the overall database storage you use.  

## Exceeding capacity quota

Exceeding the paid database storage limit won't interrupt transaction processing within the existing environments. The existing environments that organically grow and eventually exceed the quota will still be accessible and available for the customers to continue their business operations. You won't be automatically charged for the extra storage occupied by these environments.

However, once the capacity limits are exceeded, the customers won't be able to create new environments or copy their existing environments until the storage used by the existing environments is decreased to fit the quota or additional capacity is purchased. These operations will also be blocked for the customers who have more environments than they're entitled to, according to their subscription and purchased environment add-ons.  

## Reducing data stored in databases

There are a few things that you can do to reduce the amount of data stored in a database to keep it under its current limit. For more information, see [Reducing Data Stored in Databases](database-reduce-data.md).

## See also
 
[Working with Administration Tools](administration.md)  
[The Business Central Administration Center](tenant-admin-center.md)  
[Managing Environments](tenant-admin-center-environments.md)  
[Managing Apps](tenant-admin-center-manage-apps.md)  
[Updating Environments](tenant-admin-center-update-management.md)  
[Managing Tenant Notifications](tenant-admin-center-notifications.md)  
[Introduction to automation APIs](itpro-introduction-to-automation-apis.md)  
