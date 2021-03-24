---
title: Microsoft Teams へのユーザー アクセスを管理する
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: 組織内のユーザーに Teams ライセンスを割り当てまたは削除して、Teams へのユーザー アクセスを管理する方法について学習します。
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 29cf3f6816b3c1e0b00026b1ba4ad961a6a92aa6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093541"
---
# <a name="manage-user-access-to-teams"></a><span data-ttu-id="93e9f-103">Teams へのユーザー アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="93e9f-103">Manage user access to Teams</span></span>

<span data-ttu-id="93e9f-104">ユーザー レベルで Teams へのアクセスを管理するには、Microsoft Teams 製品ライセンスを割り当てるか削除します。</span><span class="sxs-lookup"><span data-stu-id="93e9f-104">You manage access to Teams at the user level by assigning or removing a Microsoft Teams product license.</span></span> <span data-ttu-id="93e9f-105">Teams 会議に匿名で参加する場合を除き、組織内の各ユーザーは Teams を使用する前に Teams ライセンスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="93e9f-105">Except for joining Teams meetings anonymously, each user in your organization must have a Teams license before they can use Teams.</span></span> <span data-ttu-id="93e9f-106">新しいユーザー アカウントが作成された場合、または既存のアカウントを持つユーザーに Teams ライセンスを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="93e9f-106">You can assign a Teams license for new users when new user accounts are created or to users with existing accounts.</span></span>

<span data-ttu-id="93e9f-107">既定では、ライセンス プラン (Microsoft 365 Enterprise E3 や Microsoft 365 Business Premium など) がユーザーに割り当てられると、Teams ライセンスが自動的に割り当て、ユーザーは Teams に対して有効になります。</span><span class="sxs-lookup"><span data-stu-id="93e9f-107">By default, when a licensing plan (for example, Microsoft 365 Enterprise E3 or Microsoft 365 Business Premium) is assigned to a user, a Teams license is automatically assigned, and the user is enabled for Teams.</span></span> <span data-ttu-id="93e9f-108">いつでもライセンスを削除または割り当てると、ユーザーの Teams を無効または有効にできます。</span><span class="sxs-lookup"><span data-stu-id="93e9f-108">You can disable or enable Teams for a user by removing or assigning a license at any time.</span></span>

<span data-ttu-id="93e9f-109"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams</a>管理センターから管理されるメッセージング ポリシーを使用して、Teams のユーザーが利用できるチャットおよびチャネル メッセージング機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="93e9f-109">Use messaging policies, managed from the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams Admin Center</a>, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="93e9f-110">既定のポリシーを使用するか、組織内のユーザー用に 1 つ以上のカスタム メッセージング ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="93e9f-110">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="93e9f-111">詳細については [、「Teams でメッセージング ポリシーを管理する」を参照してください](messaging-policies-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="93e9f-111">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>
<span data-ttu-id="93e9f-112">Teams のライセンスは、Microsoft 365 管理センターまたは PowerShell を使用して管理します。</span><span class="sxs-lookup"><span data-stu-id="93e9f-112">You manage Teams licenses in the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="93e9f-113">ライセンスを管理するには、グローバル管理者またはユーザー管理管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="93e9f-113">You must be a Global admin or User management admin to manage licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="93e9f-114">チームをプロジェクトや他の動的なイニシアティブに対して有機的に形成できるよう、すべてのユーザーに Teams を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="93e9f-114">We recommend that you enable Teams for all users so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="93e9f-115">パイロットを実行している場合でも、Teams をすべてのユーザーに対して有効にし続けるのは役に立ちますが、ユーザーのパイロット グループへの通信のみを対象とします。</span><span class="sxs-lookup"><span data-stu-id="93e9f-115">Even if you're running a pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="93e9f-116">Microsoft 365 管理センターを使用する</span><span class="sxs-lookup"><span data-stu-id="93e9f-116">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="93e9f-117">Teams のユーザー レベル ライセンスは、Microsoft 365 管理センターのユーザー管理インターフェイスを通じて直接管理されます。</span><span class="sxs-lookup"><span data-stu-id="93e9f-117">Teams user-level licenses are managed directly through the Microsoft 365 admin center user management interfaces.</span></span> <span data-ttu-id="93e9f-118">管理者は、新しいユーザー アカウントを作成するときに、または既存のアカウントを持つユーザーにライセンスを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="93e9f-118">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="93e9f-119">Microsoft Teams ライセンスを管理するには、管理者にグローバル管理者権限またはユーザー管理管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="93e9f-119">The administrator must have Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>
<span data-ttu-id="93e9f-120">Microsoft 365 管理センターを使用して、個々のユーザーまたは一度に少人数のユーザーの Teams ライセンスを管理します。</span><span class="sxs-lookup"><span data-stu-id="93e9f-120">Use the Microsoft 365 admin center to manage Teams licenses for individual users or small sets of users at a time.</span></span> <span data-ttu-id="93e9f-121">Teams のライセンスは、[ライセンス] ページ (同時に最大 20 人のユーザー) または [アクティブなユーザー]**ページで管理** できます。</span><span class="sxs-lookup"><span data-stu-id="93e9f-121">You can manage Teams licenses on the **Licenses** page (for up to 20 users at at time) or **Active users** page.</span></span> <span data-ttu-id="93e9f-122">選択する方法は、特定のユーザーの製品ライセンスを管理するか、特定の製品のユーザー ライセンスを管理するかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="93e9f-122">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="93e9f-123">数百、数千人のユーザーなど、多数のユーザーの Teams ライセンスを管理する必要がある場合は[、PowerShell または Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign)で[PowerShell](#using-powershell)またはグループベースのライセンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="93e9f-123">If you need to manage Teams licenses for a large number of users, such as hundreds or thousands of users, [use PowerShell](#using-powershell) or [group-based licensing in Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span> 

### <a name="assign-a-teams-license"></a><span data-ttu-id="93e9f-124">Teams ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="93e9f-124">Assign a Teams license</span></span>

<span data-ttu-id="93e9f-125">手順は、[ライセンス] ページと [アクティブなユーザー] ページの違い **によって異** なります。</span><span class="sxs-lookup"><span data-stu-id="93e9f-125">The steps are different depending on whether you use the **Licenses** page or **Active users** page.</span></span>  <span data-ttu-id="93e9f-126">詳しい手順については、「ライセンスをユーザーに割り当てる [」を参照してください](/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="93e9f-126">For step-by-step instructions, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

|||
|---------|---------|
|![ユーザーに対して有効になっている Teams ライセンスのスクリーンショット](media/assign-teams-licenses-1.png)    | ![ユーザーに対して有効になっている Teams ライセンスのスクリーンショット](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a><span data-ttu-id="93e9f-129">Teams のライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="93e9f-129">Remove a Teams license</span></span>

<span data-ttu-id="93e9f-130">ユーザーから Teams ライセンスを削除すると、そのユーザーの Teams は無効になり、アプリ起動ツールまたはホーム ページに Teams が表示されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="93e9f-130">When you remove a Teams license from a user, Teams is disabled for that user, and they will no longer see Teams in the app launcher or homepage.</span></span> <span data-ttu-id="93e9f-131">詳細な手順については、「ユーザーからのライセンス [の割り当て解除」を参照してください](/microsoft-365/admin/manage/remove-licenses-from-users)。</span><span class="sxs-lookup"><span data-stu-id="93e9f-131">For detailed steps, see [Unassign licenses from users](/microsoft-365/admin/manage/remove-licenses-from-users).</span></span>

|||
|---------|---------|
|![ユーザーに対して無効になっている Teams ライセンスのスクリーンショット](media/remove-teams-licenses-1.png)    | ![ユーザーに対して無効になっている Teams ライセンスのスクリーンショット](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a><span data-ttu-id="93e9f-134">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="93e9f-134">Using PowerShell</span></span>

<span data-ttu-id="93e9f-135">PowerShell を使用して、ユーザーの Teams ライセンスを一括で管理します。</span><span class="sxs-lookup"><span data-stu-id="93e9f-135">Use PowerShell to manage Teams licenses for users in bulk.</span></span> <span data-ttu-id="93e9f-136">他のサービス プラン ライセンスの場合と同じ方法で、PowerShell を使用して Teams を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="93e9f-136">You enable and disable Teams through PowerShell in the same way that you would for any other service plan license.</span></span> <span data-ttu-id="93e9f-137">Teams のサービス プランの識別子が必要です。これは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="93e9f-137">You'll need the identifiers for the service plans for Teams, which are as follows:</span></span>

- <span data-ttu-id="93e9f-138">Microsoft Teams: TEAMS1</span><span class="sxs-lookup"><span data-stu-id="93e9f-138">Microsoft Teams: TEAMS1</span></span>
- <span data-ttu-id="93e9f-139">Microsoft Teams for GCC: TEAMS_GOV</span><span class="sxs-lookup"><span data-stu-id="93e9f-139">Microsoft Teams for GCC: TEAMS_GOV</span></span>
- <span data-ttu-id="93e9f-140">Microsoft Teams for DoD: TEAMS_DOD</span><span class="sxs-lookup"><span data-stu-id="93e9f-140">Microsoft Teams for DoD: TEAMS_DOD</span></span>

### <a name="assign-teams-licenses-in-bulk"></a><span data-ttu-id="93e9f-141">Teams ライセンスを一括で割り当てる</span><span class="sxs-lookup"><span data-stu-id="93e9f-141">Assign Teams licenses in bulk</span></span>

<span data-ttu-id="93e9f-142">詳細な手順については、「PowerShell でライセンスを [ユーザー アカウントに割り当てる」を参照してください](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="93e9f-142">For detailed steps, see [Assign licenses to user accounts with PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="remove-teams-licenses-in-bulk"></a><span data-ttu-id="93e9f-143">Teams のライセンスを一括で削除する</span><span class="sxs-lookup"><span data-stu-id="93e9f-143">Remove Teams licenses in bulk</span></span>

<span data-ttu-id="93e9f-144">詳細な手順については [、「PowerShell](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) を使用してサービスへのアクセスを無効にする」および「ユーザー ライセンスの割り当て中にサービスへのアクセス [を無効にする」を参照してください](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)。</span><span class="sxs-lookup"><span data-stu-id="93e9f-144">For detailed steps, see [Disable access to services with PowerShell](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) and [Disable access to services while assigning user licenses](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span></span>

#### <a name="example"></a><span data-ttu-id="93e9f-145">例</span><span class="sxs-lookup"><span data-stu-id="93e9f-145">Example</span></span> 

<span data-ttu-id="93e9f-146">次に示すのは [、New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) コマンドレットと [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) コマンドレットを使用して、特定のライセンス プランを持つユーザーに対して Teams を無効にする方法の例です。</span><span class="sxs-lookup"><span data-stu-id="93e9f-146">The following is an example of how to use the [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) and [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) cmdlets to disable Teams for users who have a specific licensing plan.</span></span> <span data-ttu-id="93e9f-147">たとえば、次の手順に従って、特定のライセンス プランを持つすべてのユーザーに対して Teams を無効にします。</span><span class="sxs-lookup"><span data-stu-id="93e9f-147">For example, follow these steps to first disable Teams for all users who have a particular licensing plan.</span></span> <span data-ttu-id="93e9f-148">次に、Teams にアクセスする必要がある個々のユーザーごとに Teams を有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="93e9f-148">Then enable Teams for each individual user who should have access to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="93e9f-149">[New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions)コマンドレットは、カスタム スクリプトで明示的に識別されない限り、以前に無効にされたすべてのサービスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="93e9f-149">The [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) cmdlet will enable all services that were previously disabled unless explicitly identified in your custom script.</span></span> <span data-ttu-id="93e9f-150">たとえば、Exchange と Sway の両方を無効にして Teams を無効にする場合は、スクリプトにこの設定を含める必要があります。または、Exchange と Sway の両方が、特定したユーザーに対して有効になります。</span><span class="sxs-lookup"><span data-stu-id="93e9f-150">For example, if you want to leave both Exchange and Sway disabled while also disabling Teams, you'll need to include this in the script or both Exchange and Sway will be enabled for those users you identified.</span></span>

<span data-ttu-id="93e9f-151">次のコマンドを実行して、組織内で利用可能なすべてのライセンス プランを表示します。</span><span class="sxs-lookup"><span data-stu-id="93e9f-151">Run the following command to display all available licensing plans in your organization.</span></span> <span data-ttu-id="93e9f-152">詳細については [、「PowerShell でライセンスとサービスを表示する」を参照してください](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="93e9f-152">To learn more, see [View licenses and services with PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).</span></span>


```powershell
Get-MsolAccountSku
```

<span data-ttu-id="93e9f-153">前の手順で取得したライセンス計画の組織名と識別子は、次の \<CompanyName:License> コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="93e9f-153">Run the following commands, where \<CompanyName:License> is your organization name and the identifier for the licensing plan that you retrieved in the earlier step.</span></span> <span data-ttu-id="93e9f-154">たとえば、ContosoSchool:ENTERPRISEPACK_STUDENT。</span><span class="sxs-lookup"><span data-stu-id="93e9f-154">For example, ContosoSchool:ENTERPRISEPACK_STUDENT.</span></span>

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

<span data-ttu-id="93e9f-155">次のコマンドを実行して、ライセンス プランのアクティブなライセンスを持つすべてのユーザーに対して Teams を無効にします。</span><span class="sxs-lookup"><span data-stu-id="93e9f-155">Run the following command to disable Teams for all users who have an active license for the licensing plan.</span></span>

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a><span data-ttu-id="93e9f-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="93e9f-156">Related topics</span></span>

- [<span data-ttu-id="93e9f-157">Teams アドオン ライセンス</span><span class="sxs-lookup"><span data-stu-id="93e9f-157">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="93e9f-158">Teams アドオン ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="93e9f-158">Assign Teams add-on licenses</span></span>](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [<span data-ttu-id="93e9f-159">PowerShell でライセンスとサービスを表示する</span><span class="sxs-lookup"><span data-stu-id="93e9f-159">View licenses and services with PowerShell</span></span>](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="93e9f-160">ライセンスのための製品名とサービス プラン識別子</span><span class="sxs-lookup"><span data-stu-id="93e9f-160">Product names and service plan identifiers for licensing</span></span>](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="93e9f-161">Education SKU リファレンス</span><span class="sxs-lookup"><span data-stu-id="93e9f-161">Education SKU reference</span></span>](sku-reference-edu.md)