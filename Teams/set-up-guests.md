---
title: Microsoft Teams へのゲスト アクセスをオンまたはオフにする
author: LaithAlShamri
ms.author: lolaj
manager: serdars
ms.date: 10/11/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: Microsoft Teams でのゲスト アクセス機能をオンまたはオフにします。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ab67b3fa9ad58c1aa3e8fdd254e3b3515743b4c
ms.sourcegitcommit: 9dd5d8fe6888f0c7d2df1e40fdd8b4c80512f8f9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2018
ms.locfileid: "25498122"
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="cb05c-103">Microsoft Teams へのゲスト アクセスをオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="cb05c-103">Turn on or off guest access to Microsoft Teams</span></span>
======================================

<span data-ttu-id="cb05c-104">Office 365 管理者は、組織のユーザー (具体的にはチーム所有者) がゲストを追加できるようにするため事前にゲスト機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb05c-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> 

<span data-ttu-id="cb05c-105">ゲスト設定は Azure Active Directory で設定します。</span><span class="sxs-lookup"><span data-stu-id="cb05c-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="cb05c-106">その変更が Office 365 組織全体で有効になるまでに 2 時間から 24 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="cb05c-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="cb05c-107">ユーザーがチームにゲストを追加しようとするときに「Contact your administrator (管理者にお問い合わせください)」というメッセージが表示される場合、ゲスト機能が使用できる状態になっていないか、設定が有効になっていないかのいずれかの可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cb05c-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings haven’t become effective yet.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="cb05c-108">ゲスト アクセス機能の完全なエクスペリエンスを有効にするためには、Microsoft Teams、Azure Active Directory、および Office 365 の間での中心的な承認の依存関係を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="cb05c-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="cb05c-109">詳細については、「[Microsoft Teams でのゲスト アクセスを承認する](Teams-dependencies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cb05c-109">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>

## <a name="configure-guest-access-in-the-teams--skype-for-business-admin-center"></a><span data-ttu-id="cb05c-110">ビジネス管理センターのチームと Skype でゲスト アクセスを構成します。</span><span class="sxs-lookup"><span data-stu-id="cb05c-110">Configure guest access in the Teams & Skype for Business admin center</span></span>

1.  <span data-ttu-id="cb05c-111">ビジネス管理センターは、チームと Skype にサインインします。</span><span class="sxs-lookup"><span data-stu-id="cb05c-111">Sign in to the Teams & Skype for Business admin center.</span></span>

2.  <span data-ttu-id="cb05c-112">**組織全体の設定**を選択して > **のゲスト アクセス**します。</span><span class="sxs-lookup"><span data-stu-id="cb05c-112">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="cb05c-113">**マイクロソフトのチームでのゲスト アクセスを許可する**オン/オフ スイッチを**オン**に設定します。</span><span class="sxs-lookup"><span data-stu-id="cb05c-113">Set the **Allow guest access in Microsoft Teams** toggle switch to **On**.</span></span>

    ![<span data-ttu-id="cb05c-114">ゲスト アクセスのスイッチが On に設定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="cb05c-114">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="cb05c-115">**呼び出し**、**会議**、および**メッセージング**を**オン**または**オフ**をするを許可するアクセス権によって、表示を切り替えます。 を設定します。</span><span class="sxs-lookup"><span data-stu-id="cb05c-115">Set the toggles for **Calling**, **Meeting**, and **Messaging** to **On** or **Off**, depending on the access you want to allow.</span></span>

5.  <span data-ttu-id="cb05c-116">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb05c-116">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="cb05c-117">PowerShell を使用して、ゲスト アクセスを有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="cb05c-117">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="cb05c-118">ビジネス オンライン PowerShell モジュールからの Skype をダウンロードします。https://www.microsoft.com/en-us/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="cb05c-118">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/en-us/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="cb05c-119">PowerShell セッションを Skype のオンライン ビジネスのエンドポイントに接続します。</span><span class="sxs-lookup"><span data-stu-id="cb05c-119">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  <span data-ttu-id="cb05c-120">構成を確認し、`AllowGuestUser`は、 `$False`、[セット CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)コマンドレットを使用] に設定して`$True`。</span><span class="sxs-lookup"><span data-stu-id="cb05c-120">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

    ```
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
    AllowTBotProactiveMessaging      : False
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
<span data-ttu-id="cb05c-121">ゲスト ユーザーは、組織のチームのようになりましたができます。</span><span class="sxs-lookup"><span data-stu-id="cb05c-121">You can now have guest users in Teams for your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="cb05c-122">詳細情報</span><span class="sxs-lookup"><span data-stu-id="cb05c-122">More information</span></span>

<span data-ttu-id="cb05c-123">ゲスト アクセスの詳細については次のビデオを視聴します。</span><span class="sxs-lookup"><span data-stu-id="cb05c-123">Watch the following video for more details about guest access.</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="cb05c-124">Microsoft Teams でのゲストの追加</span><span class="sxs-lookup"><span data-stu-id="cb05c-124">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
