---
title: Hotfix an AppSource app
description: Learn how to hotfix an AppSource app in Dynamics 365 Business Central.
author: qutreson
ms.author: solsen
ms.reviewer: solsen
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.date: 06/12/2023
ms.custom: bap-template
---

# Hotfix an AppSource app

A `hotfix` is the submission of a new version of an AppSource app outside the planned scheduling, whether the hotfix applies to the latest major, latest minor app, or a previous version.

For example, if you have version 2.0.0.0 of your app available in AppSource and you submit a new version 1.5.0.0, then version 1.5.0.0 is considered a hotfix because 1.5.0.0 won't be the latest version available.

> [!IMPORTANT]  
> When you submit a hotfix, don't update the version of your offer in Partner Center to match the hotfix version submitted because the version shown in Partner Center on the AppSource marketplace listing shows the latest version.

> [!NOTE]  
> The concept of hotfix is tied to the country/region for which the version of your app is available. If you have different versions of your apps in some countries/regions, your submission might be a hotfix for one country/region but not another. However, we generally don't recommend having different versions per country/region.

## Against which releases is a hotfix submission validated?

When you submit a hotfix of your AppSource app, the service will automatically detect the next version available and for which release of Business Central it's available. The service will then validate your submission up to that release. The minimum release targeted by the submission is computed based on the `application` property similar to any other submission.

For example, if you have version 2.0.0.0 of your app available in AppSource that targets Business Central version 21.0, and you submit a new version 1.5.0.0 with the `application` set to 19.0.0.0, then version 1.5.0.0 will be validated for all Business Central releases from 19.0.0.0 (included) to 21.0.0.0 (excluded).

## What is the extra validation done for a hotfix submission?

To ensure your customer can upgrade from your hotfix version to the next version available in AppSource, we're validating the next version of your app for breaking changes with your hotfix version.

For example, if you have versions 1.0.0.0 and 2.0.0.0 of your app in AppSource, and you submit a new version 1.5.0.0, the technical validation will verify that:

- There are no breaking changes between 1.0.0.0 and 1.5.0.0,
- There are no breaking changes between 1.5.0.0 and 2.0.0.0.

## What kind of changes can't be part of a hotfix?

Since the AppSourceCop will validate for breaking changes, you can modify the content of your procedure. However, you can't add new AL objects or new elements (procedure, actions, fields, etc.) to your hotfix app's public API unless they're also part of the next version, or obsolete pending (except for table and table fields).

For example, let's consider that you have versions 1.0.0.0 and 2.0.0.0 of your app in AppSource.

Version 1.0.0.0 of your app is defined as follows:

```al
codeunit 1000000 MyCodeunit
{
    procedure MyPublicProcedureFromV1()
    begin
    end;
}
```

Version 2.0.0.0 of your app is defined as follows:
```al
codeunit 1000000 MyCodeunit
{
    procedure MyPublicProcedureFromV1()
    begin
    end;

    procedure MyPublicProcedureFromV2()
    begin
    end;
}
```

If you submit a new version 1.5.0.0, you're then allowed to add the following procedures:

- `local procedure MyNewLocalProcedure()` because it's not public.
- `[Obsolete] procedure MyNewObsoleteProcedure()` because it's obsolete pending.
- `MyPublicProcedureFromV2()` because it's already defined in the next version.

However, you aren't allowed to define a new procedure `procedure MyNewPublicProcedure()`, because the service detects that upgrading from version to 1.5.0.0 to version 2.0.0.0 results in the deletion of a public procedure.

## See also

[Technical Validation FAQ](devenv-checklist-submission-faq.md) 
