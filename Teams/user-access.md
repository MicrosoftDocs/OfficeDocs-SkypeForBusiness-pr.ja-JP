---
title: Microsoft Teams へのユーザー アクセスを管理する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: ユーザーごとにユーザーレベル アクセスを有効または無効にする方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 82e36e768b3e9edbf79204141540034344fb5aec
ms.sourcegitcommit: d1b14268efe334aa93a6889f25fcfe46e07d5daa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2019
ms.locfileid: "33584234"
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="7d3b3-103">Microsoft Teams へのユーザー アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="7d3b3-103">Manage user access to Microsoft Teams</span></span>
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="7d3b3-104">ユーザー レベルでは、マイクロソフトのチームへのアクセスを有効またはの割り当てまたはチームの Microsoft 製品のライセンスを削除して、ユーザーごとに無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-104">At the user level, access to Microsoft Teams can be enabled or disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="7d3b3-105">メッセージング ポリシー、管理、チーム管理センターから、チーム内のユーザーに利用可能などのようなチャットとチャネルのメッセージング機能を制御するために使用します。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-105">Use messaging policies, managed from the Teams Admin Center, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="7d3b3-106">既定のポリシーを使用したり、組織内のユーザーの 1 つまたは複数のカスタム メッセージング ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-106">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="7d3b3-107">詳細については、[チーム内のメッセージング ポリシーの管理](messaging-policies-in-teams.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-107">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>

> [!NOTE]
><span data-ttu-id="7d3b3-108">オンにするチーム、会社のすべてのユーザーのプロジェクトおよびその他の動的なイニシアティブの実施はチームを形成することができますようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-108">Microsoft recommends that you turn on Teams for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="7d3b3-109">決定する場合でも、パイロットがありますされるため、すべてのユーザーに対して有効になっているチームが、ユーザーのパイロット グループへの通信のみを対象とすると便利です。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-109">Even if you are deciding to pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="manage-teams-through-the-microsoft-365-admin-center"></a><span data-ttu-id="7d3b3-110">Microsoft 365 管理センターを使用してチームを管理します。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-110">Manage Teams through the Microsoft 365 admin center</span></span>

<span data-ttu-id="7d3b3-111">チームのユーザー レベルのライセンスは、Microsoft 365 管理センターのユーザーの管理インターフェイスを使用して直接管理されます。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-111">Teams user-level licenses are managed directly through the Microsoft 365 admin center user management interfaces.</span></span> <span data-ttu-id="7d3b3-112">管理者は、新しいユーザーの新しいユーザー アカウントを作成するときに、または既存のアカウントを持つユーザーにライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-112">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="7d3b3-113">管理者は、マイクロソフトのチームのライセンスを管理するために Office 365 のグローバル管理者またはユーザー管理者の権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-113">The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="7d3b3-p104">E3 または E5 といったライセンス SKU をユーザーに割り当てる場合、Microsoft Teams ライセンスが自動的に割り当てられ、そのユーザーには Microsoft Teams が有効化されます。管理者はすべての Office 365 サービスとライセンスを細かく制御できます。特定のユーザーまたはグループの Microsoft Teams ライセンスを有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-p104">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams. Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Office 365 管理センターの [製品ライセンス] セクションのスクリーンショット。](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="7d3b3-117">チームのユーザー ライセンスは、いつでも無効にできます。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-117">A Teams user license can be disabled at any time.</span></span> <span data-ttu-id="7d3b3-118">ライセンスを無効にすると、マイクロソフトのチームへのユーザー アクセスが禁止され、ユーザーが Office 365 アプリケーション起動ツールをクリックし、ホームページでチームを表示しなくなります。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-118">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Teams in the Office 365 app launcher and homepage.</span></span>

![Microsoft Teams が選択されていることを示す Office 365 管理センターの [製品ライセンス] セクションのスクリーンショット。](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a><span data-ttu-id="7d3b3-120">PowerShell を使用して管理します。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-120">Manage via PowerShell</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d3b3-121">MsolLicenseOptions では新しいがない限り、以前に無効にされたすべてのサービスを有効にする、カスタマイズされたスクリプトでは identitied explictitly です。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-121">New-MsolLicenseOptions will enable all services that were previously disabled unless explictitly identitied in your customized script.</span></span> <span data-ttu-id="7d3b3-122">例として、両方の Exchange & 135、139、445、チームの無効化中に無効になっている影響を与えるのままにする場合はする必要があります各自にこのスクリプトに影響を与えるが有効になりますが認められたユーザーの両方の Exchange &。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-122">As an example, if you wanted to leave both Exchange & Sway disabled while additonally disabling Teams, you'd need to inlcude this in the script or both Exchange & Sway will become enabled for those users you've identified.</span></span> <span data-ttu-id="7d3b3-123">この機能を管理するために GUI を利用する場合を参照してください: [Office 365 のライセンスのレポートおよび管理ツールを一括で削除するライセンスを割り当てる](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)</span><span class="sxs-lookup"><span data-stu-id="7d3b3-123">If you wish to do utilize a GUI to manage this functionality, See: [Office 365 License Reporting and Management Tool -Assign Remove Licenses in Bulk](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)</span></span>

<span data-ttu-id="7d3b3-124">PowerShell からワークロード ライセンスとして Teams を有効または無効にすることは、別のワークロードとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-124">Enabling and disabling Teams as a workload license through PowerShell is done just as any other workload.</span></span> <span data-ttu-id="7d3b3-125">Microsoft Teams ではサービス プランの名前は TEAMS1 になります。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-125">The service plan name is TEAMS1 for Microsoft Teams.</span></span> <span data-ttu-id="7d3b3-126">GCC のサービス計画の名前は TEAMS_GOV です。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-126">For GCC the service plan name is TEAMS_GOV.</span></span> <span data-ttu-id="7d3b3-127">GCC の高いサービス プラン名の TEAMS_GCCHIGH。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-127">For GCC High the service plan name is TEAMS_GCCHIGH.</span></span> <span data-ttu-id="7d3b3-128">DoD サービス計画の名前は TEAMS_DOD の (「」を参照[へのアクセスを無効にするには、Office 365 の PowerShell でサービス](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell)の詳細についてです。)</span><span class="sxs-lookup"><span data-stu-id="7d3b3-128">For DoD the service plan name is TEAMS_DOD (See [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) for more information.)</span></span>

<span data-ttu-id="7d3b3-129">**サンプル:** クイック サンプルだけに特定のライセンスの種類のすべてのユーザーのチームを無効する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-129">**Sample:** The following is just a quick sample on how you would disable Teams for everyone in a particular license type.</span></span> <span data-ttu-id="7d3b3-130">まずこの方法を行い、次にパイロットで使用する目的でアクセスが必要なユーザーに対して個別に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-130">You'll need to do this first, then individually enable it for the users who should have access for piloting purposes.</span></span>

<span data-ttu-id="7d3b3-131">組織内で利用可能なサブスクリプションの種類を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-131">To display the subscription types you have within your organization, use the following command:</span></span>

      Get-MsolAccountSku

<span data-ttu-id="7d3b3-132">組織名と自分の学校で使用するプランを含むプランの名前を記入します (例: ContosoSchool:ENTERPRISEPACK_STUDENT)。次に、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-132">Fill in the name of your plan that includes your organization name and the plan for your school (such as ContosoSchool:ENTERPRISEPACK_STUDENT), and then run the following commands:</span></span>

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
<span data-ttu-id="7d3b3-133">チームを名前付きのプランのアクティブなライセンスを持つすべてのユーザーを無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-133">To disable Teams for all users with an active license for your named plan, run the following command:</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="7d3b3-135">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="7d3b3-135">Decision Point</span></span>         |<ul><li><span data-ttu-id="7d3b3-136">チームの契約時に、組織の計画は、組織全体にわたって何ですか。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-136">What is your organization’s plan for Teams onboarding across the organization?</span></span>  <span data-ttu-id="7d3b3-137">パイロット (開く)</span><span class="sxs-lookup"><span data-stu-id="7d3b3-137">(Pilot or Open)</span></span></li></ul>         |
|![次のステップ アイコン。](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="7d3b3-139">次のステップ</span><span class="sxs-lookup"><span data-stu-id="7d3b3-139">Next Steps</span></span>         |<ul><li><span data-ttu-id="7d3b3-140">かどうか、ライセンスを使用して実行するか、通信を対象としたかどうか、試験運用が終了したを使用して契約時を決定します。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-140">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targeted communication.</span></span></li><li><span data-ttu-id="7d3b3-141">によって意思決定を行うパイロット ・ チームを (必要な場合) にアクセスを許可されているユーザーのみを確認する手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-141">Depending on decision, take steps to make sure only Pilot users who are allowed to access Teams (if needed).</span></span></li><li><span data-ttu-id="7d3b3-142">ユーザーの人は (表示されません) のガイドラインをドキュメント チームへのアクセスがあります。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-142">Document the guidelines for which users who will (or will not) have access to Teams.</span></span></li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a><span data-ttu-id="7d3b3-143">Office 365 テナントのレベルでチームを管理します。</span><span class="sxs-lookup"><span data-stu-id="7d3b3-143">Manage Teams at the Office 365 tenant level</span></span>
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

