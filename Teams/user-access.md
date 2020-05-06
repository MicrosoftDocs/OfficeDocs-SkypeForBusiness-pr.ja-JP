---
title: Microsoft Teams へのユーザー アクセスを管理する
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.reviewer: ritikag
search.appverid: MET150
description: 組織内のユーザーに Teams のライセンスを割り当てまたは削除して、チームへのユーザーアクセスを管理する方法について説明します。
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32ab8f68ef1c37fbb5cb724b322b4db0ee757b84
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44042274"
---
# <a name="manage-user-access-to-teams"></a><span data-ttu-id="d6aee-103">Teams へのユーザー アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="d6aee-103">Manage user access to Teams</span></span>

<span data-ttu-id="d6aee-104">Microsoft Teams 製品ライセンスを割り当てたり、削除したりして、ユーザーレベルでチームへのアクセスを管理します。</span><span class="sxs-lookup"><span data-stu-id="d6aee-104">You manage access to Teams at the user level by assigning or removing a Microsoft Teams product license.</span></span> <span data-ttu-id="d6aee-105">組織内の各ユーザーは、Teams を使用する前に Teams ライセンスを所有している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6aee-105">Each user in your organization must have a Teams license before they can use Teams.</span></span> <span data-ttu-id="d6aee-106">新しいユーザーアカウントが作成されたとき、または既存のアカウントを持つユーザーに新しいユーザーのチームライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d6aee-106">You can assign a Teams license for new users when new user accounts are created or to users with existing accounts.</span></span>

<span data-ttu-id="d6aee-107">既定では、ライセンス計画 (Microsoft 365 Enterprise E3 や Microsoft 365 Business Premium など) がユーザーに割り当てられている場合、Teams ライセンスが自動的に割り当てられ、ユーザーはチームに対して有効になります。</span><span class="sxs-lookup"><span data-stu-id="d6aee-107">By default, when a licensing plan (for example, Microsoft 365 Enterprise E3 or Microsoft 365 Business Premium)  is assigned to a user, a Teams license is automatically assigned, and the user is enabled for Teams.</span></span> <span data-ttu-id="d6aee-108">ライセンスを削除するか、いつでも割り当てて、ユーザーに対して Teams を有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d6aee-108">You can disable or enable Teams for a user by removing or assigning a license at any time.</span></span>

<span data-ttu-id="d6aee-109">Teams のライセンスは、Microsoft 365 管理センターまたは PowerShell を使用して管理します。</span><span class="sxs-lookup"><span data-stu-id="d6aee-109">You manage Teams licenses in the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="d6aee-110">ライセンスを管理するには、グローバル管理者またはユーザー管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6aee-110">You must be a Global admin or User management admin to manage licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="d6aee-111">チームがプロジェクトやその他の動的なイニシアチブのために organically を形成できるように、すべてのユーザーに対して Teams を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d6aee-111">We recommend that you enable Teams for all users so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="d6aee-112">パイロットを実行している場合でも、チームをすべてのユーザーに対して有効にしたままにしておくと便利な場合がありますが、ユーザーのパイロットグループとの通信のみを対象としています。</span><span class="sxs-lookup"><span data-stu-id="d6aee-112">Even if you're running a pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="d6aee-113">Microsoft 365 管理センターを使用する</span><span class="sxs-lookup"><span data-stu-id="d6aee-113">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="d6aee-114">Microsoft 365 管理センターを使用して、個々のユーザーまたは少数のユーザーの Teams ライセンスを一度に管理します。</span><span class="sxs-lookup"><span data-stu-id="d6aee-114">Use the Microsoft 365 admin center to manage Teams licenses for individual users or small sets of users at a time.</span></span> <span data-ttu-id="d6aee-115">Teams のライセンスは、[**ライセンス**] ページ (同時に最大20人のユーザーの場合) または [**アクティブなユーザー** ] ページで管理できます。</span><span class="sxs-lookup"><span data-stu-id="d6aee-115">You can manage Teams licenses on the **Licenses** page (for up to 20 users at at time) or **Active users** page.</span></span> <span data-ttu-id="d6aee-116">選択する方法は、特定のユーザーの製品ライセンスを管理するか、特定の製品のユーザーライセンスを管理するかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="d6aee-116">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="d6aee-117">数百または数千のユーザーなど、多数のユーザーの Teams ライセンスを管理する必要がある場合は、 [Azure Active Directory (AZURE AD) で](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)Powershell またはグループベースのライセンスを[使用](#using-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="d6aee-117">If you need to manage Teams licenses for a large number of users, such as hundreds or thousands of users, [use Powershell](#using-powershell) or [group-based licensing in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span> 

### <a name="assign-a-teams-license"></a><span data-ttu-id="d6aee-118">Teams ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="d6aee-118">Assign a Teams license</span></span>

<span data-ttu-id="d6aee-119">この手順は、[**ライセンス**] ページまたは [**アクティブなユーザー** ] ページのどちらを使用するかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="d6aee-119">The steps are different depending on whether you use the **Licenses** page or **Active users** page.</span></span>  <span data-ttu-id="d6aee-120">詳細な手順については、「[ユーザーにライセンスを割り当てる](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6aee-120">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

|||
|---------|---------|
|![ユーザーに対して有効になっている Teams ライセンスのスクリーンショット](media/assign-teams-licenses-1.png)    | ![ユーザーに対して有効になっている Teams ライセンスのスクリーンショット](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a><span data-ttu-id="d6aee-123">Teams ライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="d6aee-123">Remove a Teams license</span></span>

<span data-ttu-id="d6aee-124">ユーザーからチームライセンスを削除すると、そのユーザーに対してチームが無効になり、アプリ起動ツールまたはホームページで teams が表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="d6aee-124">When you remove a Teams license from a user, Teams is disabled for that user, and they will no longer see Teams in the app launcher or homepage.</span></span> <span data-ttu-id="d6aee-125">詳細な手順については、「[ユーザーからライセンスの割り当てを解除](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d6aee-125">For detailed steps, see [Unassign licenses from users](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users).</span></span>

|||
|---------|---------|
|![ユーザーが無効にした Teams ライセンスのスクリーンショット](media/remove-teams-licenses-1.png)    | ![ユーザーが無効にした Teams ライセンスのスクリーンショット](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a><span data-ttu-id="d6aee-128">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="d6aee-128">Using PowerShell</span></span>

<span data-ttu-id="d6aee-129">PowerShell を使用して、ユーザーの Teams ライセンスを一括で管理します。</span><span class="sxs-lookup"><span data-stu-id="d6aee-129">Use PowerShell to manage Teams licenses for users in bulk.</span></span> <span data-ttu-id="d6aee-130">他のサービスプランライセンスの場合と同様に、PowerShell を使用して Teams を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="d6aee-130">You enable and disable Teams through PowerShell in the same way that you would for any other service plan license.</span></span> <span data-ttu-id="d6aee-131">Teams のサービスプランの識別子が必要です。次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d6aee-131">You'll need the identifiers for the service plans for Teams, which are as follows:</span></span>

- <span data-ttu-id="d6aee-132">Microsoft Teams: TEAMS1</span><span class="sxs-lookup"><span data-stu-id="d6aee-132">Microsoft Teams: TEAMS1</span></span>
- <span data-ttu-id="d6aee-133">Microsoft Teams for GCC: TEAMS_GOV</span><span class="sxs-lookup"><span data-stu-id="d6aee-133">Microsoft Teams for GCC: TEAMS_GOV</span></span>
- <span data-ttu-id="d6aee-134">Microsoft Teams (DoD): TEAMS_DOD</span><span class="sxs-lookup"><span data-stu-id="d6aee-134">Microsoft Teams for DoD: TEAMS_DOD</span></span>

### <a name="assign-teams-licenses-in-bulk"></a><span data-ttu-id="d6aee-135">Teams ライセンスを一括で割り当てる</span><span class="sxs-lookup"><span data-stu-id="d6aee-135">Assign Teams licenses in bulk</span></span>

<span data-ttu-id="d6aee-136">詳細な手順については、「 [PowerShell を使用してライセンスをユーザーアカウントに割り当てる](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6aee-136">For detailed steps, see [Assign licenses to user accounts with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="remove-teams-licenses-in-bulk"></a><span data-ttu-id="d6aee-137">Teams ライセンスを一括で削除する</span><span class="sxs-lookup"><span data-stu-id="d6aee-137">Remove Teams licenses in bulk</span></span>

<span data-ttu-id="d6aee-138">詳細な手順については、「 [PowerShell を使ったサービスへのアクセスを無効に](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell)する」および「[ユーザーライセンスの割り当て中にサービスへのアクセスを無効](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)にする」を参照</span><span class="sxs-lookup"><span data-stu-id="d6aee-138">For detailed steps, see [Disable access to services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) and [Disable access to services while assigning user licenses](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span></span>

#### <a name="example"></a><span data-ttu-id="d6aee-139">例</span><span class="sxs-lookup"><span data-stu-id="d6aee-139">Example</span></span> 

<span data-ttu-id="d6aee-140">次の例は、 [MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions)と[set-msoluserlicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense)コマンドレットを使用して、特定のライセンス計画を持っているユーザーのチームを無効にする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d6aee-140">The following is an example of how to use the [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) and [Set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) cmdlets to disable Teams for users who have a specific licensing plan.</span></span> <span data-ttu-id="d6aee-141">たとえば、次の手順に従って、特定のライセンス計画を持っているすべてのユーザーに対して Teams の使用を無効にします。</span><span class="sxs-lookup"><span data-stu-id="d6aee-141">For example, follow these steps to first disable Teams for all users who have a particular licensing plan.</span></span> <span data-ttu-id="d6aee-142">次に、Teams にアクセスする必要がある個々のユーザーに対して Teams を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d6aee-142">Then enable Teams for each individual user who should have access to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6aee-143">カスタムスクリプトで明示的に指定されていない限り、 [MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions)コマンドレットによって、以前に無効になっていたすべてのサービスが有効になります。</span><span class="sxs-lookup"><span data-stu-id="d6aee-143">The [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) cmdlet will enable all services that were previously disabled unless explicitly identified in your custom script.</span></span> <span data-ttu-id="d6aee-144">たとえば、チームを無効にしている間も Exchange と Sway の両方を無効のままにしておく必要がある場合は、これをスクリプトに含めるか、または Exchange と Sway の両方を有効にして、特定のユーザーに対して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6aee-144">For example, if you want to leave both Exchange and Sway disabled while also disabling Teams, you'll need to include this in the script or both Exchange and Sway will be enabled for those users you identified.</span></span>

<span data-ttu-id="d6aee-145">次のコマンドを実行して、組織内で利用可能なすべてのライセンスプランを表示します。</span><span class="sxs-lookup"><span data-stu-id="d6aee-145">Run the following command to display all available licensing plans in your organization.</span></span> <span data-ttu-id="d6aee-146">詳細については、「 [PowerShell でライセンスとサービスを表示](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6aee-146">To learn more, see [View licenses and services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).</span></span>

      Get-MsolAccountSku

<span data-ttu-id="d6aee-147">次のコマンドを実行し\<ます。ここで、"CompanyName: ライセンス>" は、組織名と、前の手順で取得したライセンスプランの識別子です。</span><span class="sxs-lookup"><span data-stu-id="d6aee-147">Run the following commands, where \<CompanyName:License> is your organization name and the identifier for the licensing plan that you retrieved in the earlier step.</span></span> <span data-ttu-id="d6aee-148">たとえば、ContosoSchool: ENTERPRISEPACK_STUDENT とします。</span><span class="sxs-lookup"><span data-stu-id="d6aee-148">For example, ContosoSchool:ENTERPRISEPACK_STUDENT.</span></span>

      $acctSKU="<CompanyName:License>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"

<span data-ttu-id="d6aee-149">ライセンス計画のアクティブなライセンスを所有しているすべてのユーザーのチームを無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d6aee-149">Run the following command to disable Teams for all users who have an active license for the licensing plan.</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

## <a name="manage-teams-at-the-organization-level"></a><span data-ttu-id="d6aee-150">組織レベルでチームを管理する</span><span class="sxs-lookup"><span data-stu-id="d6aee-150">Manage teams at the organization level</span></span>

[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

## <a name="related-topics"></a><span data-ttu-id="d6aee-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6aee-151">Related topics</span></span>

- [<span data-ttu-id="d6aee-152">Teams アドオンライセンス</span><span class="sxs-lookup"><span data-stu-id="d6aee-152">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="d6aee-153">Teams のアドオンライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="d6aee-153">Assign Teams add-on licenses</span></span>](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [<span data-ttu-id="d6aee-154">PowerShell でライセンスとサービスを表示する</span><span class="sxs-lookup"><span data-stu-id="d6aee-154">View licenses and services with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="d6aee-155">ライセンスのための製品名とサービス プラン識別子</span><span class="sxs-lookup"><span data-stu-id="d6aee-155">Product names and service plan identifiers for licensing</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="d6aee-156">エデュケーション SKU リファレンス</span><span class="sxs-lookup"><span data-stu-id="d6aee-156">Education SKU reference</span></span>](sku-reference-edu.md)