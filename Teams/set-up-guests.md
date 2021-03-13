---
title: Microsoft Teams へのゲスト アクセスをオンまたはオフにする
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: rafarhi
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
localization_priority: Normal
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: Office 365 の管理者として Microsoft Teams のゲスト アクセス機能を有効または無効にする方法について説明します。
ms.openlocfilehash: aaf37fda456f0e48d441e78f785a3ce450f1f42c
ms.sourcegitcommit: def4b475b785a7b963f499cf9a1044e842ff66a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2021
ms.locfileid: "49786779"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="65474-103">Microsoft Teams へのゲスト アクセスをオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="65474-103">Turn on or turn off guest access to Microsoft Teams</span></span>

> [!Note]

> <span data-ttu-id="65474-104">**2021 年 2 月** まで、ゲスト アクセスは既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="65474-104">Until **February 2021**, guest access is turned off by default.</span></span> <span data-ttu-id="65474-105">管理者やチームの所有者がゲストを追加できるようにするには、Teams へのゲスト アクセスをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="65474-105">You must turn on guest access for Teams before admins or team owners can add guests.</span></span> <span data-ttu-id="65474-106">ゲストアクセスを有効にするには、変更を反映するのに、数時間かかりることもあります。</span><span class="sxs-lookup"><span data-stu-id="65474-106">After you turn on guest access, it might take a few hours for the changes to take effect.</span></span> <span data-ttu-id="65474-107">ユーザーがチームにゲストを追加しようとするときに **Contact your administrator (管理者にお問い合わせください)** というメッセージが表示される場合、ゲスト アクセスがオンになっていないか、設定が有効になっていないかのいずれかの可能性があります。</span><span class="sxs-lookup"><span data-stu-id="65474-107">If users see the message **Contact your administrator** when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span> 

> <span data-ttu-id="65474-108">**2021 年 2 月** 以降、この設定を構成していない新規のお客様と既存のお客様へは、Microsoft Teams のゲスト アクセスが既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="65474-108">After **February 2021**, guest access in Microsoft Teams will be turned on by default for new customers & existing customers who haven't configured this setting.</span></span> <span data-ttu-id="65474-109">この変更を実装すると、Microsoft Teams でゲスト アクセス機能をまだ構成していない場合、その機能はテナントで有効になります。</span><span class="sxs-lookup"><span data-stu-id="65474-109">When this change is implemented, if you've not already configured guest access capability in Microsoft Teams, that capability will be enabled in your tenant.</span></span> <span data-ttu-id="65474-110">組織でゲスト アクセスを無効にしたままにする場合は、ゲスト アクセスの設定が **既定のサービス** ではなく **オフ** に設定されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65474-110">If you want guest access to remain disabled for your organization, you'll need to confirm that the guest access setting is set to **Off** instead of **Service default**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="65474-111">ゲスト アクセスをオンにする方法は、Azure Active Directory、Office 365、SharePoint Online、Teams の設定により異なります。</span><span class="sxs-lookup"><span data-stu-id="65474-111">Turning on guest access depends on settings in Azure Active Directory, Microsoft 365, SharePoint, and Teams.</span></span> <span data-ttu-id="65474-112">詳細については、「[チームでゲストと共同作業を行う](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65474-112">For more information, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="65474-113">Teams 管理センターでゲスト アクセスを構成する</span><span class="sxs-lookup"><span data-stu-id="65474-113">Configure guest access in the Teams admin center</span></span>

1. <span data-ttu-id="65474-114">[Microsoft Teams 管理センター](https://admin.teams.microsoft.com/)にサインインする。</span><span class="sxs-lookup"><span data-stu-id="65474-114">Sign in to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

2. <span data-ttu-id="65474-115">[**組織全体の設定**] > [**ゲスト アクセス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="65474-115">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="65474-116">**[Microsoft Teams でのゲスト アクセスを許可]** を **[オン]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="65474-116">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="65474-117">ゲスト アクセスの許可の切り替えをオンに設定する</span><span class="sxs-lookup"><span data-stu-id="65474-117">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4. <span data-ttu-id="65474-118">**[通話]**、**[会議]**、および **[メッセージング]** で、ゲスト ユーザーに何を許可する必要があるかに応じて、各機能の **[オン]** または **[オフ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="65474-118">Under **Calling**, **Meeting**, and **Messaging**, select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

      - <span data-ttu-id="65474-119">**プライベート通話の発信** – この設定を [**オン**] にするとゲストがピアツーピアの通話を発信することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="65474-119">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
      - <span data-ttu-id="65474-120">**IP ビデオを許可** - この設定を [**オン**] に切り替えると、ゲストは自分たちの通話および会議でビデオを使用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="65474-120">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
      - <span data-ttu-id="65474-121">**画面共有モード** – この設定は、ゲスト ユーザーが画面共有を利用可能かどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="65474-121">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span>
          - <span data-ttu-id="65474-122">この設定を [**無効**] にすると、Teams で画面を共有するゲストの機能は削除されます。</span><span class="sxs-lookup"><span data-stu-id="65474-122">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span>
          - <span data-ttu-id="65474-123">この設定を [**1 つのアプリケーション**] にすると、個別のアプリケーションの共有を行えるようになります。</span><span class="sxs-lookup"><span data-stu-id="65474-123">Turn this setting to **Single application** to allow sharing of individual applications.</span></span>
          - <span data-ttu-id="65474-124">この設定を [**画面全体**] にすると、完全な画面共有を行えるようになります。</span><span class="sxs-lookup"><span data-stu-id="65474-124">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
      - <span data-ttu-id="65474-125">**会議の開始を許可** – この設定を [**オン**] にすると、Microsoft Teams でゲストが会議の開始機能を使用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="65474-125">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
      - <span data-ttu-id="65474-126">**送信済みメッセージの編集** - この設定を [**オン**] にすると、ゲストが以前送信したメッセージを編集することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="65474-126">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
      - <span data-ttu-id="65474-127">**ゲストによる送信済みメッセージの削除** - この設定を [**オン**] にすると、ゲストが以前送信したメッセージを削除することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="65474-127">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
      - <span data-ttu-id="65474-128">**チャット** – この設定を [**オン**] にすると、ゲストが Teams でのチャット機能を使用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="65474-128">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
      - <span data-ttu-id="65474-129">**会話で Giphys を使用する** – この設定を [**オン**] にすると、ゲストが会話で Giphys を使用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="65474-129">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="65474-130">Giphy は、ユーザーがアニメーション GIF ファイルを検索および共有することができる、オンライン データベースおよび検索エンジンです。</span><span class="sxs-lookup"><span data-stu-id="65474-130">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="65474-131">各 Giphy にはコンテンツ評価が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="65474-131">Each Giphy is assigned a content rating.</span></span>
      - <span data-ttu-id="65474-132">**Giphy のコンテンツ評価** –  ドロップダウン リストから次の評価を選択します。</span><span class="sxs-lookup"><span data-stu-id="65474-132">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
          - <span data-ttu-id="65474-133">**すべてのコンテンツを許可** - ゲストは、コンテンツ評価に関係なく、すべての Giphy をチャットに挿入することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="65474-133">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
          - <span data-ttu-id="65474-134">**中** - ゲストは、Giphy をチャットに挿入することができますが、成人向けコンテンツの挿入についてはある程度制限されます。</span><span class="sxs-lookup"><span data-stu-id="65474-134">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
          - <span data-ttu-id="65474-135">**高** - ゲストは、Giphy をチャットに挿入することができますが、成人向けコンテンツの挿入については制限されます。</span><span class="sxs-lookup"><span data-stu-id="65474-135">**Strict** – Guests can insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
      - <span data-ttu-id="65474-136">**会話でミームを使用する** – この設定を **[オン]** にすると、ゲストが会話でミームを使用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="65474-136">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
      - <span data-ttu-id="65474-137">**会話でステッカーを使用する** – この設定を [**オン**] にすると、ゲストが会話でステッカーを使用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="65474-137">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span>

    ![Teams でのゲストのアクセス権の設定](media/manage-guest-access-image1.png)

5. <span data-ttu-id="65474-139">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="65474-139">Select **Save**.</span></span>

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="65474-140">外部アクセス (フェデレーション) とゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="65474-140">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a><span data-ttu-id="65474-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="65474-141">See also</span></span>

[<span data-ttu-id="65474-142">Microsoft 365 とセキュリティで保護された共同作業を設定する</span><span class="sxs-lookup"><span data-stu-id="65474-142">Set up secure collaboration with Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[<span data-ttu-id="65474-143">特定のチームにゲストが入れないようブロックする</span><span class="sxs-lookup"><span data-stu-id="65474-143">Block guest users from a specific team</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="65474-144">Set-CsTeamsClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="65474-144">Set-CsTeamsClientConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration)
