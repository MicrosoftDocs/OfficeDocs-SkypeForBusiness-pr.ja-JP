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
description: Office 365 管理者として Microsoft Teams のゲストアクセス機能を有効または無効にする方法について説明します。
ms.openlocfilehash: 0920e9d8b8184f7f7ca83a71f0bd97d3a4d78470
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031193"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="78921-103">Microsoft Teams へのゲスト アクセスをオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="78921-103">Turn on or turn off guest access to Microsoft Teams</span></span>

<span data-ttu-id="78921-104">既定では、ゲスト アクセスはオフになっています。</span><span class="sxs-lookup"><span data-stu-id="78921-104">By default, guest access is turned off.</span></span> <span data-ttu-id="78921-105">管理者またはチーム所有者がゲストを追加する前に、チームのゲストアクセスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="78921-105">You must turn on guest access for Teams before admins or team owners can add guests.</span></span>

<span data-ttu-id="78921-106">ゲストアクセスを有効にすると、変更が反映されるまでに数時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="78921-106">After you turn on guest access, it may take a few hours for the changes to take effect.</span></span> <span data-ttu-id="78921-107">ユーザーがチームにゲストを追加しようとするときに "Contact your administrator (管理者にお問い合わせください)" というメッセージが表示される場合、ゲスト アクセスがオンになっていないか、設定が有効になっていないかのいずれかの可能性があります。</span><span class="sxs-lookup"><span data-stu-id="78921-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78921-108">ゲストアクセスを有効にするかどうかは、Azure Active Directory、Microsoft 365、SharePoint、および Teams の設定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="78921-108">Turning on guest access depends on settings in Azure Active Directory, Microsoft 365, SharePoint, and Teams.</span></span> <span data-ttu-id="78921-109">詳細については、「 [チームでゲストと共同作業](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)を行う」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78921-109">For more information, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="78921-110">Teams 管理センターでゲスト アクセスを構成する</span><span class="sxs-lookup"><span data-stu-id="78921-110">Configure guest access in the Teams admin center</span></span>

1. <span data-ttu-id="78921-111">[Microsoft Teams 管理センター](https://admin.teams.microsoft.com/)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="78921-111">Sign in to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

2. <span data-ttu-id="78921-112">[ **組織全体の設定** ] > [ **ゲスト アクセス** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="78921-112">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="78921-113">**[Microsoft Teams でのゲスト アクセスを許可]** を **[オン]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="78921-113">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="78921-114">ゲスト アクセスの許可の切り替えをオンに設定する</span><span class="sxs-lookup"><span data-stu-id="78921-114">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4. <span data-ttu-id="78921-115">**[通話]** 、 **[会議]** 、および **[メッセージング]** で、ゲスト ユーザーに何を許可する必要があるかに応じて、各機能の **[オン]** または **[オフ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="78921-115">Under **Calling** , **Meeting** , and **Messaging** , select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

      - <span data-ttu-id="78921-116">**プライベート通話の発信** – この設定を [ **オン** ] にするとゲストがピアツーピアの通話を発信することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="78921-116">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
      - <span data-ttu-id="78921-117">**IP ビデオを許可** - この設定を [ **オン** ] に切り替えると、ゲストは自分たちの通話および会議でビデオを使用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="78921-117">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
      - <span data-ttu-id="78921-118">**画面共有モード** – この設定は、ゲスト ユーザーが画面共有を利用可能かどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="78921-118">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
          - <span data-ttu-id="78921-119">この設定を [ **無効** ] にすると、Teams で画面を共有するゲストの機能は削除されます。</span><span class="sxs-lookup"><span data-stu-id="78921-119">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
          - <span data-ttu-id="78921-120">この設定を [ **1 つのアプリケーション** ] にすると、個別のアプリケーションの共有を行えるようになります。</span><span class="sxs-lookup"><span data-stu-id="78921-120">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
          - <span data-ttu-id="78921-121">この設定を [ **画面全体** ] にすると、完全な画面共有を行えるようになります。</span><span class="sxs-lookup"><span data-stu-id="78921-121">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
      - <span data-ttu-id="78921-122">**会議の開始を許可** – この設定を [ **オン** ] にすると、Microsoft Teams でゲストが会議の開始機能を使用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="78921-122">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
      - <span data-ttu-id="78921-123">**送信済みメッセージの編集** - この設定を [ **オン** ] にすると、ゲストが以前送信したメッセージを編集することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="78921-123">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
      - <span data-ttu-id="78921-124">**ゲストによる送信済みメッセージの削除** - この設定を [ **オン** ] にすると、ゲストが以前送信したメッセージを削除することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="78921-124">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
      - <span data-ttu-id="78921-125">**チャット** – この設定を [ **オン** ] にすると、ゲストが Teams でのチャット機能を使用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="78921-125">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
      - <span data-ttu-id="78921-126">**会話で Giphys を使用する** – この設定を [ **オン** ] にすると、ゲストが会話で Giphys を使用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="78921-126">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="78921-127">Giphy は、ユーザーがアニメーション GIF ファイルを検索および共有することができる、オンライン データベースおよび検索エンジンです。</span><span class="sxs-lookup"><span data-stu-id="78921-127">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="78921-128">各 Giphy にはコンテンツ評価が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="78921-128">Each Giphy is assigned a content rating.</span></span>
      - <span data-ttu-id="78921-129">**Giphy のコンテンツ評価** –  ドロップダウン リストから次の評価を選択します。</span><span class="sxs-lookup"><span data-stu-id="78921-129">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
          - <span data-ttu-id="78921-130">**すべてのコンテンツを許可** - ゲストは、コンテンツ評価に関係なく、すべての Giphy をチャットに挿入することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="78921-130">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
          - <span data-ttu-id="78921-131">**中** - ゲストは、Giphy をチャットに挿入することができますが、成人向けコンテンツの挿入についてはある程度制限されます。</span><span class="sxs-lookup"><span data-stu-id="78921-131">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
          - <span data-ttu-id="78921-132">**高** - ゲストは、Giphy をチャットに挿入することができますが、成人向けコンテンツの挿入については制限されます。</span><span class="sxs-lookup"><span data-stu-id="78921-132">**Strict** – Guests will be able to insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
      - <span data-ttu-id="78921-133">**会話でミームを使用する** – この設定を **[オン]** にすると、ゲストが会話でミームを使用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="78921-133">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
      - <span data-ttu-id="78921-134">**会話でステッカーを使用する** – この設定を [ **オン** ] にすると、ゲストが会話でステッカーを使用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="78921-134">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 

    ![Teams でのゲストのアクセス権の設定](media/manage-guest-access-image1.png)

5. <span data-ttu-id="78921-136">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="78921-136">Click **Save**.</span></span>

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="78921-137">外部アクセス (フェデレーション) とゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="78921-137">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a><span data-ttu-id="78921-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="78921-138">See also</span></span>

[<span data-ttu-id="78921-139">Microsoft 365 とのセキュリティで保護されたコラボレーションを設定する</span><span class="sxs-lookup"><span data-stu-id="78921-139">Set up secure collaboration with Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[<span data-ttu-id="78921-140">特定のチームからのゲストユーザーをブロックする</span><span class="sxs-lookup"><span data-stu-id="78921-140">Block guest users from a specific team</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="78921-141">Set-CsTeamsClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="78921-141">Set-CsTeamsClientConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration)
