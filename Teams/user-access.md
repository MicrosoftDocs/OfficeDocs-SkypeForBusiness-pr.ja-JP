---
title: "Microsoft Teams へのユーザー アクセスを管理する | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "ユーザーごとにユーザーレベル アクセスを有効または無効にする方法について説明します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: d1a0262aa41a6e7bbd2d6891c26baf9976ce86c5
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2017
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="5cdb9-103">Microsoft Teams へのユーザー アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="5cdb9-103">Manage user access to Microsoft Teams</span></span>
=====================================

<span data-ttu-id="5cdb9-104">Microsoft Teams へのユーザーレベルのアクセスは、Microsoft Teams 製品ライセンスの割り当てと削除によってユーザーごとに有効化または無効化することができます。</span><span class="sxs-lookup"><span data-stu-id="5cdb9-104">At the user-level, access to Microsoft Teams can be enabled of disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="5cdb9-105">現時点では、ライセンス以外の手段を使用して、個々のユーザーの Microsoft Teams または Microsoft Teams 機能のサブセットをオンまたはオフにするポリシー オプションはありません。</span><span class="sxs-lookup"><span data-stu-id="5cdb9-105">Currently, there are no policy options for turning Microsoft Teams, or a subset of Microsoft Teams features on or off at an individual user level outside of licensing.</span></span>

| | |
|---------|---------|
|![](media/Manage_user_access_to_Microsoft_Teams_image1.png)<br></br><span data-ttu-id="5cdb9-106">注意</span><span class="sxs-lookup"><span data-stu-id="5cdb9-106">Note</span></span> |<span data-ttu-id="5cdb9-p101">会社のすべてのユーザーに対して Microsoft Teams を有効にすることをお勧めします。そうすることで、プロジェクトやその他の動的なイニシアチブで組織的にチームを編成することが可能になります。パイロットを行う場合でも、すべてのユーザーで Microsoft Teams を有効のままにしておき、パイロット グループのユーザーに対してのみ通信を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5cdb9-p101">Microsoft recommends that Microsoft Teams is enabled for all users in a company so that teams can be formed organically for projects and other dynamic initiatives. Even if you are deciding to pilot, it may still be helpful to keep Microsoft Teams enabled for all users, but only target communications to the pilot group of users.</span></span> |

<span data-ttu-id="5cdb9-p102">Microsoft Teams のユーザーレベルのライセンスは Office 365 管理センターのユーザー管理インターフェースから直接行います。管理者は、新しいユーザー アカウントを作成するときに新しいユーザーにライセンスを割り当てたり、既存のアカウントのユーザーにライセンスを割り当てることができます。Microsoft Teams のライセンスを管理する管理者は Office 365 グローバル管理またはユーザー管理の管理者の権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="5cdb9-p102">Microsoft Teams user-level licenses are managed directly through the Office 365 admin center user management interfaces. An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts. The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="5cdb9-p103">E3 または E5 といったライセンス SKU をユーザーに割り当てる場合、Microsoft Teams ライセンスが自動的に割り当てられ、そのユーザーには Microsoft Teams が有効化されます。管理者はすべての Office 365 サービスとライセンスを細かく制御できます。特定のユーザーまたはグループの Microsoft Teams ライセンスを有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="5cdb9-p103">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams. Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

<span data-ttu-id="5cdb9-114">![](media/Manage_user_access_to_Microsoft_Teams_image2.png) ![](media/Manage_user_access_to_Microsoft_Teams_image3.png)</span><span class="sxs-lookup"><span data-stu-id="5cdb9-114">![](media/Manage_user_access_to_Microsoft_Teams_image2.png) ![](media/Manage_user_access_to_Microsoft_Teams_image3.png)</span></span>

<span data-ttu-id="5cdb9-p104">Microsoft Teams のユーザー ライセンスはいつでも無効にできます。いったん無効にすると、そのユーザーは Microsoft Teams にアクセスできなくなり、Office 365 アプリのランチャーやホームページで Microsoft Teams を表示できなくなります。</span><span class="sxs-lookup"><span data-stu-id="5cdb9-p104">A Microsoft Teams user license can be disabled at any time. Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Microsoft Teams in the Office 365 app launcher and homepage.</span></span>

![](media/Manage_user_access_to_Microsoft_Teams_image4.png)

<span data-ttu-id="5cdb9-p105">Office 365 の管理者は、Office 365 管理センターに加えて、Office 365 PowerShell を使用してもライセンスの割り当てと割り当て解除を行うことができます。ユーザーにライセンスを割り当てるには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="5cdb9-p105">In addition to using the Office 365 admin center, Office 365 admins can also use Office 365 PowerShell to assign and remove licenses. To assign a license to a user, use the following syntax:</span></span>

<span data-ttu-id="5cdb9-119">Set-MsolUserLicense -UserPrincipalName "\<Account\>" -AddLicenses "\<AccountSkuId\>"</span><span class="sxs-lookup"><span data-stu-id="5cdb9-119">Set-MsolUserLicense -UserPrincipalName "\<Account\>" -AddLicenses "\<AccountSkuId\>"</span></span>

<span data-ttu-id="5cdb9-120">次の例では、litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) ライセンス プランのライセンスを、ライセンスのないユーザー belindan@litwareinc.com に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5cdb9-120">The following example assigns a license from the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) licensing plan to the unlicensed user belindan@litwareinc.com.</span></span>

<span data-ttu-id="5cdb9-121">Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"</span><span class="sxs-lookup"><span data-stu-id="5cdb9-121">Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"</span></span>

<span data-ttu-id="5cdb9-122">詳細と例については、「[*Office 365 PowerShell を使用してライセンスをユーザー アカウントに割り当てる*](https://go.microsoft.com/fwlink/?linkid=855755)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5cdb9-122">For more details and examples, see [*Assign licenses to user accounts with Office 365 PowerShell*](https://go.microsoft.com/fwlink/?linkid=855755).</span></span>

<span data-ttu-id="5cdb9-123">既存のユーザー アカウントからライセンスを割り当て解除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="5cdb9-123">To remove licenses from an existing user account, use the following syntax:</span></span>

<span data-ttu-id="5cdb9-124">Set-MsolUserLicense -UserPrincipalName \<Account\> -RemoveLicenses "\<AccountSkuId1\>", "\<AccountSkuId2\>"</span><span class="sxs-lookup"><span data-stu-id="5cdb9-124">Set-MsolUserLicense -UserPrincipalName \<Account\> -RemoveLicenses "\<AccountSkuId1\>", "\<AccountSkuId2\>"</span></span>

<span data-ttu-id="5cdb9-125">次の例では、litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) ライセンスを、ユーザー アカウントBelindaN@litwareinc.com から割り当て解除します。</span><span class="sxs-lookup"><span data-stu-id="5cdb9-125">The following example removes the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) license from the user account BelindaN@litwareinc.com.</span></span>

<span data-ttu-id="5cdb9-126">Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"</span><span class="sxs-lookup"><span data-stu-id="5cdb9-126">Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"</span></span>

<span data-ttu-id="5cdb9-127">詳細と例については、「[*Office 365 PowerShell を使用してライセンスをユーザー アカウントから割り当て解除する*](https://go.microsoft.com/fwlink/?linkid=855756)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5cdb9-127">For more details and examples, see [*Remove licenses from user accounts with office 365 PowerShell*](https://go.microsoft.com/fwlink/?linkid=855756).</span></span>

| | | |
|---------|---------|---------|
|![](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="5cdb9-128">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="5cdb9-128">Decision Point</span></span>         |<ul><li><span data-ttu-id="5cdb9-p106">組織全体での Microsoft Teams への関与を促進するための計画を教えてください (パイロットまたはオープン)。</span><span class="sxs-lookup"><span data-stu-id="5cdb9-p106">What is your organization’s plan for Microsoft Teams onboarding across the organization?  (Pilot or Open)</span></span></li></ul>         |
|![](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="5cdb9-131">次のステップ</span><span class="sxs-lookup"><span data-stu-id="5cdb9-131">Next Steps</span></span>         |<ul><li><span data-ttu-id="5cdb9-132">閉じられたパイロットで関与促進を行う場合は、ライセンスまたは対象を絞った通信のいずれかの手段で実施するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="5cdb9-132">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targetted communication.</span></span></li><li><span data-ttu-id="5cdb9-133">この決定に応じて、Microsoft Teams へのアクセスが許可されているユーザーがパイロット ユーザーのみであることを確認する手順を行います (必要な場合)。</span><span class="sxs-lookup"><span data-stu-id="5cdb9-133">Depending on decision, take steps to make sure only Pilot users who are allowed to access Microsoft Teams (if needed).</span></span></li><li><span data-ttu-id="5cdb9-134">次の資料を使用して、Microsoft Teams にアクセスできる (またはアクセスできない) ユーザー向けのガイドラインを文書化します。</span><span class="sxs-lookup"><span data-stu-id="5cdb9-134">Document the guidelines for which users who will (or will not) have access to Microsoft Teams below.</span></span></li></ul>         |
