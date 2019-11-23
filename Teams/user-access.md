---
title: Microsoft Teams へのユーザー アクセスを管理する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
f1keywords: ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.reviewer: ritikag
search.appverid: MET150
description: ユーザーごとにユーザーレベル アクセスを有効または無効にする方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 11ec004e98c54f8b8e81594c54407fd2078c7f80
ms.sourcegitcommit: 5a7e273a3636322052e4a48a5a75513cbf5abb84
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "39209073"
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="8c123-103">Microsoft Teams へのユーザー アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="8c123-103">Manage user access to Microsoft Teams</span></span>
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="8c123-104">ユーザーレベルでは、microsoft Teams 製品ライセンスを割り当てまたは削除することで、ユーザーごとに Microsoft Teams へのアクセスを有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="8c123-104">At the user level, access to Microsoft Teams can be enabled or disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="8c123-105">Teams 管理センターから管理されるメッセージポリシーを使用して、Teams のユーザーが利用できるチャットおよびチャネルメッセージング機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="8c123-105">Use messaging policies, managed from the Teams Admin Center, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="8c123-106">組織内のユーザーに対して、既定のポリシーを使用するか、1つ以上のカスタムメッセージポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="8c123-106">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="8c123-107">詳細については、「 [Teams のメッセージングポリシーを管理する」](messaging-policies-in-teams.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c123-107">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>

> [!NOTE]
><span data-ttu-id="8c123-108">組織内のすべてのユーザーに対して Teams を有効にすることをお勧めします。これにより、チームはプロジェクトやその他の動的なイニシアチブの organically を形成することができます。</span><span class="sxs-lookup"><span data-stu-id="8c123-108">Microsoft recommends that you turn on Teams for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="8c123-109">パイロットを決定している場合でも、チームをすべてのユーザーに対して有効にしておくことをお勧めしますが、ユーザーのパイロットグループとの通信のみを対象としています。</span><span class="sxs-lookup"><span data-stu-id="8c123-109">Even if you are deciding to pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="manage-teams-through-the-microsoft-365-admin-center"></a><span data-ttu-id="8c123-110">Microsoft 365 管理センターを使用してチームを管理する</span><span class="sxs-lookup"><span data-stu-id="8c123-110">Manage Teams through the Microsoft 365 admin center</span></span>

<span data-ttu-id="8c123-111">Teams のユーザーレベルのライセンスは、Microsoft 365 管理センターのユーザー管理インターフェイスを使用して直接管理されます。</span><span class="sxs-lookup"><span data-stu-id="8c123-111">Teams user-level licenses are managed directly through the Microsoft 365 admin center user management interfaces.</span></span> <span data-ttu-id="8c123-112">管理者は、新しいユーザーアカウントが作成されたとき、または既存のアカウントを持つユーザーに対して、新しいユーザーにライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8c123-112">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="8c123-113">管理者は、Microsoft Teams のライセンスを管理するための Office 365 グローバル管理者またはユーザー管理者の権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c123-113">The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="8c123-p104">E3 または E5 といったライセンス SKU をユーザーに割り当てる場合、Microsoft Teams ライセンスが自動的に割り当てられ、そのユーザーには Microsoft Teams が有効化されます。管理者はすべての Office 365 サービスとライセンスを細かく制御できます。特定のユーザーまたはグループの Microsoft Teams ライセンスを有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="8c123-p104">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams. Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![管理センターの [製品ライセンス] セクションのスクリーンショット。](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="8c123-117">Teams ユーザーライセンスは、いつでも無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="8c123-117">A Teams user license can be disabled at any time.</span></span> <span data-ttu-id="8c123-118">ライセンスを無効にすると、ユーザーは Microsoft Teams へのアクセスを許可されなくなり、Office 365 アプリ起動ツールとホームページで Teams を表示することはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="8c123-118">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Teams in the Office 365 app launcher and homepage.</span></span>

![[製品のライセンス] セクションで選択された Teams を示すスクリーンショット。](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a><span data-ttu-id="8c123-120">PowerShell を使用して管理する</span><span class="sxs-lookup"><span data-stu-id="8c123-120">Manage via PowerShell</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c123-121">MsolLicenseOptions を使うと、カスタマイズされたスクリプトに explictitly 識別子が関連付けられていない限り、以前に無効になったすべてのサービスを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="8c123-121">New-MsolLicenseOptions will enable all services that were previously disabled unless explictitly identitied in your customized script.</span></span> <span data-ttu-id="8c123-122">たとえば、additonally を無効にしている間も Exchange & Sway をすべて残しておく必要がある場合は、これをスクリプトに含めるか、または両方とも Exchange & Sway が有効になっているユーザーを確認します。</span><span class="sxs-lookup"><span data-stu-id="8c123-122">As an example, if you wanted to leave both Exchange & Sway disabled while additonally disabling Teams, you'd need to include this in the script or both Exchange & Sway will become enabled for those users you've identified.</span></span> <span data-ttu-id="8c123-123">GUI を使ってこの機能を管理する方法については、「 [Office 365 ライセンスレポートと管理ツール-一括](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)してライセンスを削除する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c123-123">To use a GUI to manage this functionality, see [Office 365 License Reporting and Management Tool -Assign Remove Licenses in Bulk](https://gallery.technet.microsoft.com/Office365-License-cfd9489c) for more information.</span></span>

<span data-ttu-id="8c123-124">PowerShell からワークロード ライセンスとして Teams を有効または無効にすることは、別のワークロードとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="8c123-124">Enabling and disabling Teams as a workload license through PowerShell is done just as any other workload.</span></span> <span data-ttu-id="8c123-125">Microsoft Teams ではサービス プランの名前は TEAMS1 になります。</span><span class="sxs-lookup"><span data-stu-id="8c123-125">The service plan name is TEAMS1 for Microsoft Teams.</span></span> <span data-ttu-id="8c123-126">GCC の場合、サービスプラン名は TEAMS_GOV です。</span><span class="sxs-lookup"><span data-stu-id="8c123-126">For GCC the service plan name is TEAMS_GOV.</span></span> <span data-ttu-id="8c123-127">GCC 高の場合、サービスプラン名は TEAMS_GCCHIGH。</span><span class="sxs-lookup"><span data-stu-id="8c123-127">For GCC High the service plan name is TEAMS_GCCHIGH.</span></span> <span data-ttu-id="8c123-128">DoD の場合、サービスプラン名は TEAMS_DOD (詳細については、「 [Office 365 PowerShell でサービスへのアクセスを無効](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell)にする」を参照してください。)</span><span class="sxs-lookup"><span data-stu-id="8c123-128">For DoD the service plan name is TEAMS_DOD (See [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) for more information.)</span></span>

<span data-ttu-id="8c123-129">**サンプル:** 次に示すのは、特定のライセンスの種類のすべてのユーザーに対して Teams を無効にする方法の簡単なサンプルです。</span><span class="sxs-lookup"><span data-stu-id="8c123-129">**Sample:** The following is just a quick sample on how you would disable Teams for everyone in a particular license type.</span></span> <span data-ttu-id="8c123-130">まずこの方法を行い、次にパイロットで使用する目的でアクセスが必要なユーザーに対して個別に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c123-130">You'll need to do this first, then individually enable it for the users who should have access for piloting purposes.</span></span>

<span data-ttu-id="8c123-131">組織内で利用可能なサブスクリプションの種類を表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8c123-131">To display the subscription types you have within your organization, use the following command:</span></span>

      Get-MsolAccountSku

<span data-ttu-id="8c123-132">組織名と自分の学校で使用するプランを含むプランの名前を記入します (例: ContosoSchool:ENTERPRISEPACK_STUDENT)。次に、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8c123-132">Fill in the name of your plan that includes your organization name and the plan for your school (such as ContosoSchool:ENTERPRISEPACK_STUDENT), and then run the following commands:</span></span>

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
<span data-ttu-id="8c123-133">指定したプランのアクティブなライセンスを持つすべてのユーザーのチームを無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8c123-133">To disable Teams for all users with an active license for your named plan, run the following command:</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![判断ポイントを表すアイコン](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="8c123-135">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="8c123-135">Decision Point</span></span>         |<ul><li><span data-ttu-id="8c123-136">組織全体でのチームのオンボードの計画はどのようなものですか?</span><span class="sxs-lookup"><span data-stu-id="8c123-136">What is your organization’s plan for Teams onboarding across the organization?</span></span>  <span data-ttu-id="8c123-137">(パイロットまたはオープン)</span><span class="sxs-lookup"><span data-stu-id="8c123-137">(Pilot or Open)</span></span></li></ul>         |
|![次の手順を示すアイコン](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="8c123-139">次のステップ</span><span class="sxs-lookup"><span data-stu-id="8c123-139">Next Steps</span></span>         |<ul><li><span data-ttu-id="8c123-140">終了したパイロットによるオンボードの場合は、ライセンスまたは対象指定の通信を使用するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="8c123-140">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targeted communication.</span></span></li><li><span data-ttu-id="8c123-141">決定に応じて、チームへのアクセスが許可されているパイロットユーザー (必要な場合) だけを確認するための手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8c123-141">Depending on decision, take steps to make sure only Pilot users who are allowed to access Teams (if needed).</span></span></li><li><span data-ttu-id="8c123-142">Teams へのアクセス権を持つ (または使用しない) ユーザーを対象としたガイドラインを文書化します。</span><span class="sxs-lookup"><span data-stu-id="8c123-142">Document the guidelines for which users who will (or will not) have access to Teams.</span></span></li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a><span data-ttu-id="8c123-143">Office 365 テナントレベルでチームを管理する</span><span class="sxs-lookup"><span data-stu-id="8c123-143">Manage Teams at the Office 365 tenant level</span></span>
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

