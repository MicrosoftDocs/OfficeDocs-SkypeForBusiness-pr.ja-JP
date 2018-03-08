---
title: "Microsoft チームのユーザー アクセスを管理します。"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "有効にする、ユーザーごとにユーザー レベルのアクセスを無効にする方法について説明します。"
ms.openlocfilehash: 66ec29077b83b799c85acce1b5869b82fb0b83f7
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="753db-103">Microsoft チームのユーザー アクセスを管理します。</span><span class="sxs-lookup"><span data-stu-id="753db-103">Manage user access to Microsoft Teams</span></span>
=====================================

<span data-ttu-id="753db-104">ユーザー レベルで Microsoft チームへのアクセスできるユーザーごとに無効の割り当てまたはチームの Microsoft 製品のライセンスを削除してできます。</span><span class="sxs-lookup"><span data-stu-id="753db-104">At the user-level, access to Microsoft Teams can be enabled of disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="753db-105">現時点では、Microsoft チーム、または Microsoft チーム機能のサブセットをオンまたはオフにライセンスの外部で個別のユーザー レベルのポリシー オプションはありません。</span><span class="sxs-lookup"><span data-stu-id="753db-105">Currently, there are no policy options for turning Microsoft Teams, or a subset of Microsoft Teams features on or off at an individual user level outside of licensing.</span></span>



> [!NOTE]
><span data-ttu-id="753db-p101">Microsoft チームが有効であるすべてのユーザー、会社のチーム プロジェクトおよび他の動的な計画の実施形成するようにすることをお勧めします。する場合でも、パイロットこともあります、すべてのユーザーを有効になっている Microsoft チームを残してのみパイロット ユーザー グループへの通信を対象にするおくと便利です。</span><span class="sxs-lookup"><span data-stu-id="753db-p101">Microsoft recommends that Microsoft Teams is enabled for all users in a company so that teams can be formed organically for projects and other dynamic initiatives. Even if you are deciding to pilot, it may still be helpful to keep Microsoft Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

<span data-ttu-id="753db-p102">Microsoft チームのユーザー レベルのライセンスについては、Office 365 管理センターのユーザーの管理インターフェイスを使用して直接管理されます。管理者は、新しいユーザー アカウントを作成するときに新しいユーザー、または既存のアカウントを持つユーザーにライセンスを割り当てることができます。管理者は、Microsoft チームのライセンスを管理する Office 365 のグローバル管理者またはユーザー管理の管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="753db-p102">Microsoft Teams user-level licenses are managed directly through the Office 365 admin center user management interfaces. An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts. The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="753db-p103">E3 など E5 SKU がユーザーに割り当てられているライセンスを Microsoft チーム ライセンスが自動的に割り当てられているし、ユーザーが Microsoft チーム用に有効にします。管理者がすべての Office 365 サービスと、ライセンスを細かく制御を設定して、特定のユーザーまたはユーザーのグループの Microsoft チーム ライセンスを有効または無効になっていることができます。</span><span class="sxs-lookup"><span data-stu-id="753db-p103">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams. Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Office 365 管理センターのライセンス] セクションの製品のスクリーン ショット。](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="753db-p104">Microsoft チームのユーザー ライセンスは、いつでも無効にすることができます。ライセンスを無効にすると、ユーザーが Microsoft チームにアクセスできませんし、ユーザーは、Office 365 アプリ起動ツールとホーム ページで Microsoft チームを表示できなきます。</span><span class="sxs-lookup"><span data-stu-id="753db-p104">A Microsoft Teams user license can be disabled at any time. Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Microsoft Teams in the Office 365 app launcher and homepage.</span></span>

![Office 365 管理センターで、選択されている Microsoft チームが表示されているライセンス] セクションの製品のスクリーン ショット。](media/Manage_user_access_to_Microsoft_Teams_image4.png)

<span data-ttu-id="753db-p105">Office 365 管理センターではなく、Office 365 の管理者は Office 365 PowerShell を割り当てるライセンスを削除しても使用できます。ライセンスをユーザーに割り当てるには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="753db-p105">In addition to using the Office 365 admin center, Office 365 admins can also use Office 365 PowerShell to assign and remove licenses. To assign a license to a user, use the following syntax:</span></span>

<span data-ttu-id="753db-119">セット MsolUserLicense UserPrincipalName"\<アカウント\>"- AddLicenses"\<AccountSkuId\>"</span><span class="sxs-lookup"><span data-stu-id="753db-119">Set-MsolUserLicense -UserPrincipalName "\<Account\>" -AddLicenses "\<AccountSkuId\>"</span></span>

<span data-ttu-id="753db-120">次の例では、ライセンスのないユーザー belindan@litwareinc.com に litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) ライセンス プランからのライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="753db-120">The following example assigns a license from the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) licensing plan to the unlicensed user belindan@litwareinc.com.</span></span>

<span data-ttu-id="753db-121">設定 MsolUserLicense-UserPrincipalName"belindan@litwareinc.com"- AddLicenses"litwareinc:ENTERPRISEPACK"</span><span class="sxs-lookup"><span data-stu-id="753db-121">Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"</span></span>

<span data-ttu-id="753db-122">その他の詳細および例では、 [*Office 365 PowerShell でのユーザー アカウントにライセンスを割り当てる*](https://go.microsoft.com/fwlink/?linkid=855755)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="753db-122">For more details and examples, see [*Assign licenses to user accounts with Office 365 PowerShell*](https://go.microsoft.com/fwlink/?linkid=855755).</span></span>

<span data-ttu-id="753db-123">既存のユーザー アカウントからライセンスを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="753db-123">To remove licenses from an existing user account, use the following syntax:</span></span>

<span data-ttu-id="753db-124">セット MsolUserLicense UserPrincipalName\<アカウント\>- RemoveLicenses"\<AccountSkuId1\>「,」\<AccountSkuId2\>"</span><span class="sxs-lookup"><span data-stu-id="753db-124">Set-MsolUserLicense -UserPrincipalName \<Account\> -RemoveLicenses "\<AccountSkuId1\>", "\<AccountSkuId2\>"</span></span>

<span data-ttu-id="753db-125">次の例では、ユーザー アカウント BelindaN@litwareinc.com から litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) ライセンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="753db-125">The following example removes the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) license from the user account BelindaN@litwareinc.com.</span></span>

<span data-ttu-id="753db-126">設定 MsolUserLicense-UserPrincipalName belindan@litwareinc.com - RemoveLicenses"litwareinc:ENTERPRISEPACK"</span><span class="sxs-lookup"><span data-stu-id="753db-126">Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"</span></span>

<span data-ttu-id="753db-127">その他の詳細および例では、 [*office がユーザーのアカウントから 365 PowerShell ライセンスを削除する*](https://go.microsoft.com/fwlink/?linkid=855756)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="753db-127">For more details and examples, see [*Remove licenses from user accounts with office 365 PowerShell*](https://go.microsoft.com/fwlink/?linkid=855756).</span></span>

| | | |
|---------|---------|---------|
|![判断するポイントをタップします。](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="753db-129">判断するポイント</span><span class="sxs-lookup"><span data-stu-id="753db-129">Decision Point</span></span>         |<ul><li><span data-ttu-id="753db-p106">Microsoft チーム オンボーディングの組織の計画は、組織全体で何ですか。 テスト導入期間 (開く)</span><span class="sxs-lookup"><span data-stu-id="753db-p106">What is your organization’s plan for Microsoft Teams onboarding across the organization?  (Pilot or Open)</span></span></li></ul>         |
|![次の手順をタップします。](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="753db-133">次のステップ</span><span class="sxs-lookup"><span data-stu-id="753db-133">Next Steps</span></span>         |<ul><li><span data-ttu-id="753db-134">閉じたパイロットを介してオンボーディングことに決めたかどうかライセンス、または対象のコミュニケーションを通じて実行する場合。</span><span class="sxs-lookup"><span data-stu-id="753db-134">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targetted communication.</span></span></li><li><span data-ttu-id="753db-135">意思決定、によってかかるのみパイロット (必要な場合) は、マイクロソフトのチームをアクセスを許可されているユーザーの手順を実行していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="753db-135">Depending on decision, take steps to make sure only Pilot users who are allowed to access Microsoft Teams (if needed).</span></span></li><li><span data-ttu-id="753db-136">ドキュメントのユーザーのユーザーが (または表示されません) のガイドラインは、次の Microsoft チームにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="753db-136">Document the guidelines for which users who will (or will not) have access to Microsoft Teams below.</span></span></li></ul>         |
