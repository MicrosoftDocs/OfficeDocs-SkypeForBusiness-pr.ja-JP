---
title: Microsoft Teams へのゲスト アクセスをオンまたはオフにする
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Microsoft Teams でのゲスト アクセス機能をオンまたはオフにします。
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5bcdbc3251820bdcee860323ad993efc8d6673c0
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41835647"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="eb0ca-103">Microsoft Teams へのゲスト アクセスをオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="eb0ca-103">Turn on or turn off guest access to Microsoft Teams</span></span>
===================================================

<span data-ttu-id="eb0ca-104">既定では、ゲスト アクセスはオフになっています。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-104">By default, guest access is turned off.</span></span> <span data-ttu-id="eb0ca-105">管理者やチームの所有者がゲストを追加できるようにするには、Office 365 管理者が Teams へのゲスト アクセスをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-105">As the Office 365 admin, you must turn on guest access for Teams before the admin or team owners can add guests.</span></span> <span data-ttu-id="eb0ca-106">ゲスト アクセスをオンにするには、[ゲスト アクセスのチェックリスト](guest-access-checklist.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-106">To turn on guest access, use the [Guest access checklist](guest-access-checklist.md).</span></span> 

<span data-ttu-id="eb0ca-107">ゲスト アクセスをオンにしてからその変更が有効になるまでに、2 から 24 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-107">After you turn on guest access, it takes 2-24 hours for the changes to take effect.</span></span> <span data-ttu-id="eb0ca-108">ユーザーがチームにゲストを追加しようとするときに "Contact your administrator (管理者にお問い合わせください)" というメッセージが表示される場合、ゲスト アクセスがオンになっていないか、設定が有効になっていないかのいずれかの可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-108">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eb0ca-109">ゲスト アクセスをオンにする方法は、Azure Active Directory、Office 365、SharePoint Online、Teams の設定により異なります。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-109">Turning on guest access depends on settings in Azure Active Directory, Office 365, SharePoint Online, and Teams.</span></span> <span data-ttu-id="eb0ca-110">詳細については、「[Microsoft Teams でのゲスト アクセスを承認する](Teams-dependencies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-110">For more information, see [Authorize guest access in Teams](Teams-dependencies.md).</span></span>



## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="eb0ca-111">Teams 管理センターでゲスト アクセスを構成する</span><span class="sxs-lookup"><span data-stu-id="eb0ca-111">Configure guest access in the Teams admin center</span></span>

1.  <span data-ttu-id="eb0ca-112">Microsoft Teams 管理センターにサインインする。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-112">Sign in to the Microsoft Teams admin center.</span></span>

2.  <span data-ttu-id="eb0ca-113">[**組織全体の設定**] > [**ゲスト アクセス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-113">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="eb0ca-114">**[Microsoft Teams でのゲスト アクセスを許可]** を **[オン]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-114">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="eb0ca-115">ゲスト アクセスの許可の切り替えをオンに設定する</span><span class="sxs-lookup"><span data-stu-id="eb0ca-115">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="eb0ca-116">**[通話]**、**[会議]**、および **[メッセージング]** で、ゲスト ユーザーに何を許可する必要があるかに応じて、各機能の **[オン]** または **[オフ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-116">Under **Calling**, **Meeting**, and **Messaging**, select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

    - <span data-ttu-id="eb0ca-117">**プライベート通話の発信** – この設定を [**オン**] にするとゲストがピアツーピアの通話を発信することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-117">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
    - <span data-ttu-id="eb0ca-118">**IP ビデオを許可** - この設定を [**オン**] に切り替えると、ゲストは自分たちの通話および会議でビデオを使用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-118">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
    - <span data-ttu-id="eb0ca-119">**画面共有モード** – この設定は、ゲスト ユーザーが画面共有を利用可能かどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-119">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
       - <span data-ttu-id="eb0ca-120">この設定を [**無効**] にすると、Teams で画面を共有するゲストの機能は削除されます。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-120">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
       - <span data-ttu-id="eb0ca-121">この設定を [**1 つのアプリケーション**] にすると、個別のアプリケーションの共有を行えるようになります。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-121">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
       - <span data-ttu-id="eb0ca-122">この設定を [**画面全体**] にすると、完全な画面共有を行えるようになります。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-122">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
    - <span data-ttu-id="eb0ca-123">**会議の開始を許可** – この設定を [**オン**] にすると、Microsoft Teams でゲストが会議の開始機能を使用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-123">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
    - <span data-ttu-id="eb0ca-124">**送信済みメッセージの編集** - この設定を [**オン**] にすると、ゲストが以前送信したメッセージを編集することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-124">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
    - <span data-ttu-id="eb0ca-125">**ゲストによる送信済みメッセージの削除** - この設定を [**オン**] にすると、ゲストが以前送信したメッセージを削除することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-125">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
    - <span data-ttu-id="eb0ca-126">**チャット** – この設定を [**オン**] にすると、ゲストが Teams でのチャット機能を使用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-126">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
    - <span data-ttu-id="eb0ca-127">**会話で Giphys を使用する** – この設定を [**オン**] にすると、ゲストが会話で Giphys を使用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-127">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="eb0ca-128">Giphy は、ユーザーがアニメーション GIF ファイルを検索および共有することができる、オンライン データベースおよび検索エンジンです。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-128">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="eb0ca-129">各 Giphy にはコンテンツ評価が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-129">Each Giphy is assigned a content rating.</span></span>
    - <span data-ttu-id="eb0ca-130">**Giphy のコンテンツ評価** –  ドロップダウン リストから次の評価を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-130">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
       - <span data-ttu-id="eb0ca-131">**すべてのコンテンツを許可** - ゲストは、コンテンツ評価に関係なく、すべての Giphy をチャットに挿入することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-131">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
       - <span data-ttu-id="eb0ca-132">**中** - ゲストは、Giphy をチャットに挿入することができますが、成人向けコンテンツの挿入についてはある程度制限されます。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-132">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
       - <span data-ttu-id="eb0ca-133">**高** - ゲストは、Giphy をチャットに挿入することができますが、成人向けコンテンツの挿入については制限されます。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-133">**Strict** – Guests will be able to insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
    - <span data-ttu-id="eb0ca-134">**会話でミームを使用する** – この設定を **[オン]** にすると、ゲストが会話でミームを使用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-134">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
    - <span data-ttu-id="eb0ca-135">**会話でステッカーを使用する** – この設定を [**オン**] にすると、ゲストが会話でステッカーを使用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-135">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 


5.  <span data-ttu-id="eb0ca-136">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-136">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="eb0ca-137">PowerShell を使用してゲスト アクセスをオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="eb0ca-137">Use PowerShell to turn guest access on or off</span></span>
<span data-ttu-id="eb0ca-138">「[PowerShell を使用してゲスト アクセスをオンまたはオフにする](guest-access-PowerShell.md#use-powershell-to-turn-guest-access-on-or-off)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb0ca-138">Read [Use PowerShell to turn guest access on or off](guest-access-PowerShell.md#use-powershell-to-turn-guest-access-on-or-off)</span></span>


## <a name="video-adding-guests-in-teams"></a><span data-ttu-id="eb0ca-139">ビデオ: Teams でのゲストの追加</span><span class="sxs-lookup"><span data-stu-id="eb0ca-139">Video: Adding guests in Teams</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="eb0ca-140">Microsoft Teams でのゲストの追加</span><span class="sxs-lookup"><span data-stu-id="eb0ca-140">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 


## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="eb0ca-141">外部アクセス (フェデレーション) とゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="eb0ca-141">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]