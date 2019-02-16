---
title: Microsoft Teams でのゲスト アクセス
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/25/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
search.appverid: MET150
description: Microsoft Teams でのゲスト アクセスにより、組織内のチームは組織外の人にチームおよびチャネルへのアクセス権を付与することで、それらの人と共同作業することができるようになります。
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: c8b7bcf1951da82b85b9541ee2e4ec0e8216ede4
ms.sourcegitcommit: 6d4b99de7233e91dbab4f08331dac4d88c51d9e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2019
ms.locfileid: "30059026"
---
<a name="guest-access-in-microsoft-teams"></a>Microsoft Teams でのゲスト アクセス
======================================

## <a name="guest-access-overview"></a>ゲスト アクセスの概要

Guest access is one of the features customers asked for the most. Here’s how you can keep up with our progress on guest access and tell us your thoughts:

- ゲスト アクセスに関して問題がある場合は、「[Microsoft Teams の既知の問題](Known-issues.md)」を確認してください。
- 今後実装される新機能や更新された機能については、「[Teams のロードマップ](https://aka.ms/teamsroadmap)」で見つけてください。
- ご要望については、「[Teams UserVoice](https://aka.ms/TeamsUserVoice)」でお知らせください。
- 下にある [コメント] セクションでお客様ご自身のエクスペリエンスを共有してください。

Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels on one or more of your tenants. Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.

Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions with no additional licensing requirement. You can have up to 5 guests per licensed user on your tenant. For more information about licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance). 

Guest access is a tenant-level setting in Microsoft Teams and is turned off by default. Guest access is subject to Azure AD and Office 365 service limits.

> [!NOTE]
> Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization. For these users to use Teams, they must be assigned an Office 365 Business Premium, Office 365 Enterprise, or Office 365 Education subscription. 

## <a name="who-is-a-guest"></a>ゲストとは何ですか?

A guest is someone who isn't an employee, student, or member of your organization. They don't have a school or work account with your organization. For example, guests may include partners, vendors, suppliers, or consultants. Anyone who is not part of your organization can be added as guest in Teams. This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences. (You can read about guest restrictions in [Authorize guest access in Microsoft Teams](teams-dependencies.md).) All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.

## <a name="why-use-guest-access"></a>ゲスト アクセスを使用する理由を教えてください。
      
With guest access, organizations that use Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data. All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.  

Teams is built on Office 365 Groups and provides a new way to access shared assets for an Office 365 group. Teams is the best solution for persistent chat among group/team members. Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely. 

## <a name="how-does-guest-access-compare-to-external-access-federation"></a>ゲスト アクセスは (連合) の外部アクセスをどのような比較をするでしょうか。

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a>詳細情報
    
[Microsoft Teams のサポート リソース](support-resources.md)  
[Office 365 グループのゲスト アクセス](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
|  |  |
|---------|---------|
|Introduction to guest access (ゲスト アクセスの概要)   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
|Deep dive into Guest Access (ゲスト アクセスの詳細)   | <iframe width="350" height="200" src="https://www.youtube.com/embed/vaJRRSjBxxY" frameborder="0" allowfullscreen></iframe>   |
| Adding guests in Microsoft Teams (Microsoft Teams でのゲストの追加)   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    

