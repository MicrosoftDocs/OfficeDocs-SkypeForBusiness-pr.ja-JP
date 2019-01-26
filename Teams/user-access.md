---
title: Microsoft Teams へのユーザー アクセスを管理する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: ritikag
search.appverid: MET150
description: ユーザーごとにユーザーレベル アクセスを有効または無効にする方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: be2e95d7be359856d5aef4f67664ef27ee62fa74
ms.sourcegitcommit: c0679cbaf7df38769f722afd65c4232311d25515
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2019
ms.locfileid: "29562614"
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="440e2-103">Microsoft Teams へのユーザー アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="440e2-103">Manage user access to Microsoft Teams</span></span>
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="440e2-104">ユーザー レベルでは、マイクロソフトのチームへのアクセスを有効またはの割り当てまたはチームの Microsoft 製品のライセンスを削除して、ユーザーごとに無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="440e2-104">At the user level, access to Microsoft Teams can be enabled or disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="440e2-105">現時点では、チーム、またはチームの機能のサブセット オンまたはオフにライセンス以外では、個々 のユーザー レベルのポリシーのオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="440e2-105">Currently, there are no policy options for turning Teams, or a subset of Teams features, on or off at an individual user level outside of licensing.</span></span>

> [!NOTE]
><span data-ttu-id="440e2-106">オンにするチーム、会社のすべてのユーザーのプロジェクトおよびその他の動的なイニシアティブの実施はチームを形成することができますようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="440e2-106">Microsoft recommends that you turn on Teams for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="440e2-107">決定する場合でも、パイロットがありますされるため、すべてのユーザーに対して有効になっているチームが、ユーザーのパイロット グループへの通信のみを対象とすると便利です。</span><span class="sxs-lookup"><span data-stu-id="440e2-107">Even if you are deciding to pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="manage-teams-through-the-office-365-admin-center"></a><span data-ttu-id="440e2-108">Office 365 管理センターを使用してチームを管理します。</span><span class="sxs-lookup"><span data-stu-id="440e2-108">Manage Teams through the Office 365 admin center</span></span>

<span data-ttu-id="440e2-109">チームのユーザー レベルのライセンスは、Office 365 管理センターのユーザーの管理インターフェイスを使用して直接管理されます。</span><span class="sxs-lookup"><span data-stu-id="440e2-109">Teams user-level licenses are managed directly through the Office 365 admin center user management interfaces.</span></span> <span data-ttu-id="440e2-110">管理者は、新しいユーザーの新しいユーザー アカウントを作成するときに、または既存のアカウントを持つユーザーにライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="440e2-110">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="440e2-111">管理者は、マイクロソフトのチームのライセンスを管理するために Office 365 のグローバル管理者またはユーザー管理者の権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="440e2-111">The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="440e2-p103">E3 または E5 といったライセンス SKU をユーザーに割り当てる場合、Microsoft Teams ライセンスが自動的に割り当てられ、そのユーザーには Microsoft Teams が有効化されます。管理者はすべての Office 365 サービスとライセンスを細かく制御できます。特定のユーザーまたはグループの Microsoft Teams ライセンスを有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="440e2-p103">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams. Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Office 365 管理センターの [製品ライセンス] セクションのスクリーンショット。](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="440e2-115">チームのユーザー ライセンスは、いつでも無効にできます。</span><span class="sxs-lookup"><span data-stu-id="440e2-115">A Teams user license can be disabled at any time.</span></span> <span data-ttu-id="440e2-116">ライセンスを無効にすると、マイクロソフトのチームへのユーザー アクセスが禁止され、ユーザーが Office 365 アプリケーション起動ツールをクリックし、ホームページでチームを表示しなくなります。</span><span class="sxs-lookup"><span data-stu-id="440e2-116">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Teams in the Office 365 app launcher and homepage.</span></span>

![Microsoft Teams が選択されていることを示す Office 365 管理センターの [製品ライセンス] セクションのスクリーンショット。](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a><span data-ttu-id="440e2-118">PowerShell を使用して管理します。</span><span class="sxs-lookup"><span data-stu-id="440e2-118">Manage via PowerShell</span></span>

> [!IMPORTANT]
> <span data-ttu-id="440e2-119">MsolLicenseOptions では新しいがない限り、以前に無効にされたすべてのサービスを有効にする、カスタマイズされたスクリプトでは identitied explictitly です。</span><span class="sxs-lookup"><span data-stu-id="440e2-119">New-MsolLicenseOptions will enable all services that were previously disabled unless explictitly identitied in your customized script.</span></span> <span data-ttu-id="440e2-120">例として、両方の Exchange & 135、139、445、チームの無効化中に無効になっている影響を与えるのままにする場合はする必要があります各自にこのスクリプトに影響を与えるが有効になりますが認められたユーザーの両方の Exchange &。</span><span class="sxs-lookup"><span data-stu-id="440e2-120">As an example, if you wanted to leave both Exchange & Sway disabled while additonally disabling Teams, you'd need to inlcude this in the script or both Exchange & Sway will become enabled for those users you've identified.</span></span> <span data-ttu-id="440e2-121">この機能を管理するために GUI を利用する場合を参照してください: [Office 365 のライセンスのレポートおよび管理ツールを一括で削除するライセンスを割り当てる](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)</span><span class="sxs-lookup"><span data-stu-id="440e2-121">If you wish to do utilize a GUI to manage this functionality, See: [Office 365 License Reporting and Management Tool -Assign Remove Licenses in Bulk](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)</span></span>

<span data-ttu-id="440e2-122">PowerShell からワークロード ライセンスとして Teams を有効または無効にすることは、別のワークロードとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="440e2-122">Enabling and disabling Teams as a workload license through PowerShell is done just as any other workload.</span></span> <span data-ttu-id="440e2-123">Microsoft Teams ではサービス プランの名前は TEAMS1 になります。</span><span class="sxs-lookup"><span data-stu-id="440e2-123">The service plan name is TEAMS1 for Microsoft Teams.</span></span> <span data-ttu-id="440e2-124">政府サービス計画の名前は TEAMS_GOV です。</span><span class="sxs-lookup"><span data-stu-id="440e2-124">For Government the service plan name is TEAMS_GOV.</span></span> <span data-ttu-id="440e2-125">(詳細については、「[Office 365 PowerShell を使用してサービスへのアクセスを無効にする](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell)」をご覧ください。)</span><span class="sxs-lookup"><span data-stu-id="440e2-125">(See [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) for more information.)</span></span>

<span data-ttu-id="440e2-126">**サンプル:** クイック サンプルだけに特定のライセンスの種類のすべてのユーザーのチームを無効する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="440e2-126">**Sample:** The following is just a quick sample on how you would disable Teams for everyone in a particular license type.</span></span> <span data-ttu-id="440e2-127">まずこの方法を行い、次にパイロットで使用する目的でアクセスが必要なユーザーに対して個別に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="440e2-127">You'll need to do this first, then individually enable it for the users who should have access for piloting purposes.</span></span>

<span data-ttu-id="440e2-128">組織内で利用可能なサブスクリプションの種類を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="440e2-128">To display the subscription types you have within your organization, use the following command:</span></span>

      Get-MsolAccountSku

<span data-ttu-id="440e2-129">組織名と自分の学校で使用するプランを含むプランの名前を記入します (例: ContosoSchool:ENTERPRISEPACK_STUDENT)。次に、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="440e2-129">Fill in the name of your plan that includes your organization name and the plan for your school (such as ContosoSchool:ENTERPRISEPACK_STUDENT), and then run the following commands:</span></span>

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
<span data-ttu-id="440e2-130">チームを名前付きのプランのアクティブなライセンスを持つすべてのユーザーを無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="440e2-130">To disable Teams for all users with an active license for your named plan, run the following command:</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="440e2-132">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="440e2-132">Decision Point</span></span>         |<ul><li><span data-ttu-id="440e2-133">チームの契約時に、組織の計画は、組織全体にわたって何ですか。</span><span class="sxs-lookup"><span data-stu-id="440e2-133">What is your organization’s plan for Teams onboarding across the organization?</span></span>  <span data-ttu-id="440e2-134">パイロット (開く)</span><span class="sxs-lookup"><span data-stu-id="440e2-134">(Pilot or Open)</span></span></li></ul>         |
|![次のステップ アイコン。](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="440e2-136">次のステップ</span><span class="sxs-lookup"><span data-stu-id="440e2-136">Next Steps</span></span>         |<ul><li><span data-ttu-id="440e2-137">かどうか、ライセンスを使用して実行するか、通信を対象としたかどうか、試験運用が終了したを使用して契約時を決定します。</span><span class="sxs-lookup"><span data-stu-id="440e2-137">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targeted communication.</span></span></li><li><span data-ttu-id="440e2-138">によって意思決定を行うパイロット ・ チームを (必要な場合) にアクセスを許可されているユーザーのみを確認する手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="440e2-138">Depending on decision, take steps to make sure only Pilot users who are allowed to access Teams (if needed).</span></span></li><li><span data-ttu-id="440e2-139">ユーザーの人は (表示されません) のガイドラインをドキュメント チームへのアクセスがあります。</span><span class="sxs-lookup"><span data-stu-id="440e2-139">Document the guidelines for which users who will (or will not) have access to Teams.</span></span></li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a><span data-ttu-id="440e2-140">Office 365 テナントのレベルでチームを管理します。</span><span class="sxs-lookup"><span data-stu-id="440e2-140">Manage Teams at the Office 365 tenant level</span></span>
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

