---
title: Microsoft Teams へのゲスト アクセスをオンまたはオフにする
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 10/18/2018
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
ms.openlocfilehash: 42fead56b8064d2697ca4e8b115eefd0116a5e36
ms.sourcegitcommit: 454ded73af5854d7b81a3b996702a6464b3fc313
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2019
ms.locfileid: "27772762"
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="548a4-103">Microsoft Teams へのゲスト アクセスをオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="548a4-103">Turn on or off guest access to Microsoft Teams</span></span>
======================================

<span data-ttu-id="548a4-104">Office 365 管理者は、組織のユーザー (具体的にはチーム所有者) がゲストを追加できるようにするため事前にゲスト機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="548a4-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> 

<span data-ttu-id="548a4-105">ゲスト設定は Azure Active Directory で設定します。</span><span class="sxs-lookup"><span data-stu-id="548a4-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="548a4-106">その変更が Office 365 組織全体で有効になるまでに 2 時間から 24 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="548a4-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="548a4-107">ユーザーが「管理者に問い合わせてください」メッセージを表示するかどうかはゲスト機能を有効になっていないか、またはいる設定がまだ有効な可能性がありますが、自分のチームにゲストを追加しようとするとします。</span><span class="sxs-lookup"><span data-stu-id="548a4-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings aren't effective yet.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="548a4-108">ゲスト アクセス機能の完全なエクスペリエンスを有効にするためには、Microsoft Teams、Azure Active Directory、および Office 365 の間での中心的な承認の依存関係を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="548a4-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="548a4-109">詳細については、「[Microsoft Teams でのゲスト アクセスを承認する](Teams-dependencies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="548a4-109">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>

## <a name="configure-guest-access-in-the-teams--skype-for-business-admin-center"></a><span data-ttu-id="548a4-110">ビジネス管理センターのチームと Skype でゲスト アクセスを構成します。</span><span class="sxs-lookup"><span data-stu-id="548a4-110">Configure guest access in the Teams & Skype for Business admin center</span></span>

1.  <span data-ttu-id="548a4-111">ビジネス管理センターは、チームと Skype にサインインします。</span><span class="sxs-lookup"><span data-stu-id="548a4-111">Sign in to the Teams & Skype for Business admin center.</span></span>

2.  <span data-ttu-id="548a4-112">**組織全体の設定**を選択して > **のゲスト アクセス**します。</span><span class="sxs-lookup"><span data-stu-id="548a4-112">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="548a4-113">**マイクロソフトのチームでのゲスト アクセスを許可する**オン/オフ スイッチを**オン**に設定します。</span><span class="sxs-lookup"><span data-stu-id="548a4-113">Set the **Allow guest access in Microsoft Teams** toggle switch to **On**.</span></span>

    ![<span data-ttu-id="548a4-114">ゲスト アクセスのスイッチが On に設定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="548a4-114">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="548a4-115">ゲスト ユーザーを許可する機能によって**オン**または**オフ**を**呼び出し**、**会議**、および**メッセージ**の表示を切り替えます。 を設定します。</span><span class="sxs-lookup"><span data-stu-id="548a4-115">Set the toggles under **Calling**, **Meeting**, and **Messaging** to **On** or **Off**, depending on the capabilities you want to allow for guest users.</span></span>

    - <span data-ttu-id="548a4-116">**秘密の呼び出しを行う**: ピア ツー ピアの呼び出しを行うには、来園者を許可する**に**は、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="548a4-116">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
    - <span data-ttu-id="548a4-117">**IP ビデオを許可する**が、通話や会議でビデオを使用するには、来園者を許可する**に**は、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="548a4-117">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
    - <span data-ttu-id="548a4-118">**画面モードを共有する**: この設定は、画面をゲスト ユーザーの共有の可用性を制御します。</span><span class="sxs-lookup"><span data-stu-id="548a4-118">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
       - <span data-ttu-id="548a4-119">**無効になっている**チームでの画面を共有するには、来園者の機能を削除するには、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="548a4-119">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
       - <span data-ttu-id="548a4-120">個々 のアプリケーションの共有を許可する**単一のアプリケーション**にこの設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="548a4-120">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
       - <span data-ttu-id="548a4-121">**全体の画面**の完了] 画面の共有を許可するのには、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="548a4-121">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
    - <span data-ttu-id="548a4-122">**により即時**に即時会議の機能を使用して、マイクロソフトのチームでは、来園者を許可する**上で**この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="548a4-122">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
    - <span data-ttu-id="548a4-123">**編集メッセージを送信する**-この設定**を**編集するには、来園者を許可するが、メッセージを有効にする送信済みです。</span><span class="sxs-lookup"><span data-stu-id="548a4-123">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
    - <span data-ttu-id="548a4-124">以前に送信を**来園者が送信したメッセージを削除できます**: この設定**を**削除するには、来園者を許可するが、メッセージを有効にするには。</span><span class="sxs-lookup"><span data-stu-id="548a4-124">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
    - <span data-ttu-id="548a4-125">**チャット**– を提供する**上で**この設定を有効にするには、チームでのチャットを使用することが来園者します。</span><span class="sxs-lookup"><span data-stu-id="548a4-125">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
    - <span data-ttu-id="548a4-126">**会話に Giphys を使用して**– 会話で Giphys を使用するには、来園者を許可する**に**は、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="548a4-126">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="548a4-127">Giphy は、オンライン データベースと検索エンジンを検索し、アニメーション GIF ファイルを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="548a4-127">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="548a4-128">各 Giphy は、コンテンツの格付けを割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="548a4-128">Each Giphy is assigned a content rating.</span></span>
    - <span data-ttu-id="548a4-129">**Giphy コンテンツの規制**: ドロップ ダウン リストからレベルを選択:</span><span class="sxs-lookup"><span data-stu-id="548a4-129">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
       - <span data-ttu-id="548a4-130">**すべてのコンテンツを許可する**、来園者はコンテンツの規制に関係なく、チャットのすべての Giphys を挿入するのにはできるようになります。</span><span class="sxs-lookup"><span data-stu-id="548a4-130">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
       - <span data-ttu-id="548a4-131">**中程度**の来園者は、チャット、Giphys を挿入することになりますが、成人向けコンテンツからやや制限されています。</span><span class="sxs-lookup"><span data-stu-id="548a4-131">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
       - <span data-ttu-id="548a4-132">**Strict** : 来園者は、チャット、Giphys を挿入することになりますが、成人向けコンテンツを挿入することから厳密に制限されます。</span><span class="sxs-lookup"><span data-stu-id="548a4-132">**Strict** – Guests will be able to insert Giphys in chats, but will be strictly restricted from inserting adult content.</span></span>
    - <span data-ttu-id="548a4-133">**Memes の会話の中を使用して**の会話に Memes を使用するには、来園者を許可する**に**は、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="548a4-133">**Use Memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
    - <span data-ttu-id="548a4-134">**会話にステッカーを使用して**– 会話にステッカーを使用するには、来園者を許可する**に**は、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="548a4-134">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 


5.  <span data-ttu-id="548a4-135">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="548a4-135">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="548a4-136">PowerShell を使用して、ゲスト アクセスを有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="548a4-136">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="548a4-137">ビジネス オンライン PowerShell モジュールからの Skype をダウンロードします。https://www.microsoft.com/en-us/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="548a4-137">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/en-us/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="548a4-138">PowerShell セッションを Skype のオンライン ビジネスのエンドポイントに接続します。</span><span class="sxs-lookup"><span data-stu-id="548a4-138">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  <span data-ttu-id="548a4-139">構成を確認し、`AllowGuestUser`は、 `$False`、[セット CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)コマンドレットを使用] に設定して`$True`。</span><span class="sxs-lookup"><span data-stu-id="548a4-139">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

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
<span data-ttu-id="548a4-140">ゲスト ユーザーは、組織のチームのようになりましたができます。</span><span class="sxs-lookup"><span data-stu-id="548a4-140">You can now have guest users in Teams for your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="548a4-141">詳細情報</span><span class="sxs-lookup"><span data-stu-id="548a4-141">More information</span></span>

<span data-ttu-id="548a4-142">ゲスト アクセスの詳細については次のビデオを視聴します。</span><span class="sxs-lookup"><span data-stu-id="548a4-142">Watch the following video for more details about guest access.</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="548a4-143">Microsoft Teams でのゲストの追加</span><span class="sxs-lookup"><span data-stu-id="548a4-143">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
