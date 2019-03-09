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
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d7fb3479c8230735d04494bd6aacfbd8d3d23395
ms.sourcegitcommit: f3b41e7abafc84571bd9e8267d41decc0fe78e4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2019
ms.locfileid: "30493574"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="7f0ae-103">Microsoft Teams でのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="7f0ae-103">Guest access in Microsoft Teams</span></span>
======================================

## <a name="guest-access-overview"></a><span data-ttu-id="7f0ae-104">ゲスト アクセスの概要</span><span class="sxs-lookup"><span data-stu-id="7f0ae-104">Guest access overview</span></span>

<span data-ttu-id="7f0ae-105">Guest access is one of the features customers asked for the most.</span><span class="sxs-lookup"><span data-stu-id="7f0ae-105">Guest access is one of the features customers asked for the most.</span></span> <span data-ttu-id="7f0ae-106">Here’s how you can keep up with our progress on guest access and tell us your thoughts:</span><span class="sxs-lookup"><span data-stu-id="7f0ae-106">Here’s how you can keep up with our progress on guest access and tell us your thoughts:</span></span>

- <span data-ttu-id="7f0ae-107">ゲスト アクセスに関して問題がある場合は、「[Microsoft Teams の既知の問題](Known-issues.md)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="7f0ae-107">If you’re having trouble with Guest Access, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="7f0ae-108">今後実装される新機能や更新された機能については、「[Teams のロードマップ](https://aka.ms/teamsroadmap)」で見つけてください。</span><span class="sxs-lookup"><span data-stu-id="7f0ae-108">Find out about upcoming new or updated features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="7f0ae-109">ご要望については、「[Teams UserVoice](https://aka.ms/TeamsUserVoice)」でお知らせください。</span><span class="sxs-lookup"><span data-stu-id="7f0ae-109">Tell us what you want in  [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>
- <span data-ttu-id="7f0ae-110">下にある [コメント] セクションでお客様ご自身のエクスペリエンスを共有してください。</span><span class="sxs-lookup"><span data-stu-id="7f0ae-110">Share your experience in the Comments section below.</span></span>

<span data-ttu-id="7f0ae-111">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels on one or more of your tenants.</span><span class="sxs-lookup"><span data-stu-id="7f0ae-111">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels on one or more of your tenants.</span></span> <span data-ttu-id="7f0ae-112">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span><span class="sxs-lookup"><span data-stu-id="7f0ae-112">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span>

<span data-ttu-id="7f0ae-113">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions with no additional licensing requirement.</span><span class="sxs-lookup"><span data-stu-id="7f0ae-113">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions with no additional licensing requirement.</span></span> <span data-ttu-id="7f0ae-114">You can have up to 5 guests per licensed user on your tenant.</span><span class="sxs-lookup"><span data-stu-id="7f0ae-114">You can have up to 5 guests per licensed user on your tenant.</span></span> <span data-ttu-id="7f0ae-115">For more information about licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="7f0ae-115">For more information about licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).</span></span> 

<span data-ttu-id="7f0ae-116">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span><span class="sxs-lookup"><span data-stu-id="7f0ae-116">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span> <span data-ttu-id="7f0ae-117">Guest access is subject to Azure AD and Office 365 service limits.</span><span class="sxs-lookup"><span data-stu-id="7f0ae-117">Guest access is subject to Azure AD and Office 365 service limits.</span></span>

> [!NOTE]
> <span data-ttu-id="7f0ae-118">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span><span class="sxs-lookup"><span data-stu-id="7f0ae-118">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="7f0ae-119">For these users to use Teams, they must be assigned an Office 365 Business Premium, Office 365 Enterprise, or Office 365 Education subscription.</span><span class="sxs-lookup"><span data-stu-id="7f0ae-119">For these users to use Teams, they must be assigned an Office 365 Business Premium, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="7f0ae-120">ゲストとは何ですか?</span><span class="sxs-lookup"><span data-stu-id="7f0ae-120">Who is a guest?</span></span>

<span data-ttu-id="7f0ae-121">A guest is someone who isn't an employee, student, or member of your organization.</span><span class="sxs-lookup"><span data-stu-id="7f0ae-121">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="7f0ae-122">They don't have a school or work account with your organization.</span><span class="sxs-lookup"><span data-stu-id="7f0ae-122">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="7f0ae-123">For example, guests may include partners, vendors, suppliers, or consultants.</span><span class="sxs-lookup"><span data-stu-id="7f0ae-123">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="7f0ae-124">Anyone who is not part of your organization can be added as guest in Teams.</span><span class="sxs-lookup"><span data-stu-id="7f0ae-124">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="7f0ae-125">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span><span class="sxs-lookup"><span data-stu-id="7f0ae-125">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span> <span data-ttu-id="7f0ae-126">(You can read about guest restrictions in [Authorize guest access in Microsoft Teams](teams-dependencies.md).) All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7f0ae-126">(You can read about guest restrictions in [Authorize guest access in Microsoft Teams](teams-dependencies.md).) All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="7f0ae-127">ゲスト アクセスを使用する理由を教えてください。</span><span class="sxs-lookup"><span data-stu-id="7f0ae-127">Why use guest access?</span></span>
      
<span data-ttu-id="7f0ae-128">With guest access, organizations that use Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span><span class="sxs-lookup"><span data-stu-id="7f0ae-128">With guest access, organizations that use Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="7f0ae-129">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7f0ae-129">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span>  

<span data-ttu-id="7f0ae-130">Teams is built on Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span><span class="sxs-lookup"><span data-stu-id="7f0ae-130">Teams is built on Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="7f0ae-131">Teams is the best solution for persistent chat among group/team members.</span><span class="sxs-lookup"><span data-stu-id="7f0ae-131">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="7f0ae-132">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span><span class="sxs-lookup"><span data-stu-id="7f0ae-132">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span> 

## <a name="how-does-guest-access-compare-to-external-access-federation"></a><span data-ttu-id="7f0ae-133">ゲスト アクセスは (連合) の外部アクセスをどのような比較をするでしょうか。</span><span class="sxs-lookup"><span data-stu-id="7f0ae-133">How does guest access compare to external access (federation)?</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="7f0ae-134">詳細情報</span><span class="sxs-lookup"><span data-stu-id="7f0ae-134">More information</span></span>
    
[<span data-ttu-id="7f0ae-135">Microsoft Teams のサポート リソース</span><span class="sxs-lookup"><span data-stu-id="7f0ae-135">Support resources for Microsoft Teams</span></span>](support-resources.md)  
[<span data-ttu-id="7f0ae-136">Office 365 グループのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="7f0ae-136">Guest access in Office 365 Groups</span></span>](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
|  |  |
|---------|---------|
|<span data-ttu-id="7f0ae-137">Introduction to guest access (ゲスト アクセスの概要)</span><span class="sxs-lookup"><span data-stu-id="7f0ae-137">Introduction to to guest access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
|<span data-ttu-id="7f0ae-138">Deep dive into Guest Access (ゲスト アクセスの詳細)</span><span class="sxs-lookup"><span data-stu-id="7f0ae-138">Deep dive into guest access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/vaJRRSjBxxY" frameborder="0" allowfullscreen></iframe>   |
| <span data-ttu-id="7f0ae-139">Adding guests in Microsoft Teams (Microsoft Teams でのゲストの追加)</span><span class="sxs-lookup"><span data-stu-id="7f0ae-139">Adding guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    

