---
title: "OnClosePage Trigger"
description: "OnClosePage trigger in AL for Business Central."
ms.custom: na
ms.date: 04/01/2021
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: reference
author: SusanneWindfeldPedersen
---

# OnClosePage Trigger

Runs as a page closes after the [OnQueryClosePage Trigger](devenv-onqueryclosepage-trigger.md) is executed.  

## Syntax  

```AL
trigger OnClosePage()
begin
    ...
end;
```  

## Applies to  

- Pages  

<!--NAV
> [!IMPORTANT]  
>  The OnClosePage trigger is not fully supported by the [!INCLUDE[nav_web](../includes/nav_web_md.md)]. When the page displays in the [!INCLUDE[nav_web](../includes/nav_web_md.md)], the trigger is only invoked when the page is hosted in a modal popup window \(MPO\).
-->  

> [!IMPORTANT]  
> The trigger is only invoked when the page is hosted in a modal popup window \(MPO\).

## Remarks

This trigger is initiated by a user action, such as when the user chooses the **Close** button, or by the CurrPage.CLOSE  being called.  

You can write to the database from this trigger.

## See Also  

[Triggers](devenv-triggers.md)  
[OnQueryClosePage Trigger](devenv-onqueryclosepage-trigger.md)  
[Page and Action Triggers](devenv-page-and-action-triggers.md)  