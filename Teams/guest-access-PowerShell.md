---
title: PowerShell を使用してチームへのゲスト アクセスを制御する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
f1.keywords:
- NOCSH
description: PowerShell を使用して、Microsoft Teams のすべてのチームまたは特定のチームへのゲストアクセスを許可またはブロックする方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0c8a2e23f5c03420c4b0ce644a80e0733f9f69a5
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814336"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="2fb04-103">PowerShell を使用してチームへのゲスト アクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="2fb04-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="2fb04-104">Microsoft 365 管理センターと Azure Active Directory (Azure AD) ポータルのほかに、Windows PowerShell を使用してゲストアクセスを制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="2fb04-104">In addition to using the Microsoft 365 admin center and the Azure Active Directory (Azure AD) portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="2fb04-105">PowerShell を使用すると、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2fb04-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="2fb04-106">すべてのチームと Microsoft 365 グループへのゲストアクセスを許可またはブロックする</span><span class="sxs-lookup"><span data-stu-id="2fb04-106">Allow or block guest access to all teams and Microsoft 365 Groups</span></span>

- <span data-ttu-id="2fb04-107">すべてのチームと Microsoft 365 グループにゲストを追加できるようにする</span><span class="sxs-lookup"><span data-stu-id="2fb04-107">Allow guests to be added to all teams and Microsoft 365 Groups</span></span>

- <span data-ttu-id="2fb04-108">特定のチームまたは Microsoft 365 グループからのゲストユーザーを許可またはブロックする</span><span class="sxs-lookup"><span data-stu-id="2fb04-108">Allow or block guest users from a specific team or Microsoft 365 group</span></span>

<span data-ttu-id="2fb04-109">詳細については、「 [Microsoft 365 グループでゲストアクセスを管理](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups)する」の「PowerShell を使用してゲストアクセスを制御する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fb04-109">For details, see "Use PowerShell to control guest access" in [Manage guest access in Microsoft 365 Groups](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups).</span></span>

  
<span data-ttu-id="2fb04-110">PowerShell を使用して、ドメインに基づいてゲスト ユーザーの許可と拒否を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="2fb04-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="2fb04-111">たとえば、ある企業 (Contoso) が別の企業 (Fabrikam) とパートナーシップを結んでいると仮定します。</span><span class="sxs-lookup"><span data-stu-id="2fb04-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="2fb04-112">Fabrikam 社を [許可] リストに追加すると、Contoso 社のユーザーは Fabrikam のユーザーをゲストとしてグループに追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2fb04-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="2fb04-113">詳細については、「 [Microsoft 365 グループへのゲストアクセスを許可/ブロックする](https://go.microsoft.com/fwlink/?linkid=854001)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fb04-113">For more information, see [Allow/Block guest access to Microsoft 365 Groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="2fb04-114">チーム内のゲストをブロックし、それでも SharePoint サイトへのアクセスを許可する場合は、Azure AD PowerShell コマンドレットを使用して、SharePoint サイトの外部共有が有効になっていることを前提として、Company オブジェクトの AllowGuestsToAccessGroups パラメーターを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="2fb04-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure AD PowerShell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="2fb04-115">PowerShell を使用してゲスト アクセスをオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="2fb04-115">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="2fb04-116">Skype for Business Online PowerShell モジュールを次からダウンローします https://www.microsoft.com/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="2fb04-116">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="2fb04-117">PowerShell セッションを Skype for Business Online エンドポイントに接続します。</span><span class="sxs-lookup"><span data-stu-id="2fb04-117">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

> [!NOTE]
> <span data-ttu-id="2fb04-118">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="2fb04-118">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="2fb04-119">最新の [Teams PowerShell パブリックリリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)を使用している場合は、Skype For Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2fb04-119">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

    ```powershell
    Import-Module -Name MicrosoftTeams
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
    
3.  <span data-ttu-id="2fb04-120">設定を確認して、`AllowGuestUser` が `$False` の場合は、[Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) コマンドレットを使用して `$True` に設定します。</span><span class="sxs-lookup"><span data-stu-id="2fb04-120">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

    ```powershell
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
<span data-ttu-id="2fb04-121">これで、自分の組織の Teams にゲスト ユーザーを入れることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2fb04-121">You can now have guest users in Teams for your organization.</span></span>


## <a name="guest-access-vs-external-access"></a><span data-ttu-id="2fb04-122">ゲストアクセスと外部アクセス</span><span class="sxs-lookup"><span data-stu-id="2fb04-122">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
