---
title: Microsoft Teams でのデスクトップ共有を構成する
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
description: チームのチャットまたは会議でユーザーがデスクトップを共有できるように会議ポリシーを構成する方法について説明します。
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 34d7780e1d10370b78c11c1a8021381aff71f479
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552593"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="04c51-103">Microsoft Teams でのデスクトップ共有を構成する</span><span class="sxs-lookup"><span data-stu-id="04c51-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="04c51-104">デスクトップを共有すると、ユーザーは会議やチャット中に画面やアプリを表示できます。</span><span class="sxs-lookup"><span data-stu-id="04c51-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="04c51-105">管理者が Microsoft Teams で画面共有を構成すると、ユーザーは画面全体、アプリ、ファイルを共有できるようになります。</span><span class="sxs-lookup"><span data-stu-id="04c51-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="04c51-106">ユーザーによる制御の付与または要求の許可、PowerPoint 共有の許可、ホワイトボードの追加、共有メモの許可を設定できます。</span><span class="sxs-lookup"><span data-stu-id="04c51-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="04c51-107">匿名ユーザーや外部ユーザーが共有画面の制御を要求できるかどうかも構成できます。</span><span class="sxs-lookup"><span data-stu-id="04c51-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="04c51-108">画面共有を構成するには、新しい会議ポリシーを作成し、そのポリシーを管理対象ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="04c51-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="04c51-109">**[Microsoft Teams 管理センター](https://admin.teams.microsoft.com/)で**</span><span class="sxs-lookup"><span data-stu-id="04c51-109">**In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/)**</span></span>

1. <span data-ttu-id="04c51-110">**[会議]** > **[会議ポリシー]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="04c51-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![選択された会議ポリシーを示すスクリーン ショット](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="04c51-112">**[会議ポリシー]** ページで、**[新しいポリシー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="04c51-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![会議ポリシーのメッセージを示すスクリーン ショット](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="04c51-114">ポリシーに一意のタイトルを指定し、簡単な説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="04c51-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="04c51-115">**[コンテンツの共有]** の下にある、**[画面共有モード]** ドロップダウン リストから選択します。</span><span class="sxs-lookup"><span data-stu-id="04c51-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="04c51-116">**[画面全体]**: ユーザーはデスクトップ全体を共有できます。</span><span class="sxs-lookup"><span data-stu-id="04c51-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="04c51-117">**[1 つのアプリケーション]**: ユーザーの画面共有は 1 つのアクティブなアプリケーションに制限されます。</span><span class="sxs-lookup"><span data-stu-id="04c51-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="04c51-118">**[無効]**: 画面共有をオフにします。</span><span class="sxs-lookup"><span data-stu-id="04c51-118">**Disabled** – Turns off screen sharing.</span></span>

    ![共有モード オプションを示すスクリーン ショット](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="04c51-120">次の設定をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="04c51-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="04c51-121">**参加者による制御の付与または要求を許可する**–チームのメンバーが、発表者のデスクトップまたはアプリケーションの制御を付与または要求できるようにします。</span><span class="sxs-lookup"><span data-stu-id="04c51-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter's desktop or application.</span></span>
    - <span data-ttu-id="04c51-122">**外部参加者による制御の付与または要求を許可する**–これはユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="04c51-122">**Allow an external participant to give or request control** – This is a per-user policy.</span></span> <span data-ttu-id="04c51-123">組織がユーザーに対してこのセットを持っているかどうかは、会議の開催者によって設定されているかどうかに関係なく、外部の参加者が実行できる操作を制御しません。</span><span class="sxs-lookup"><span data-stu-id="04c51-123">Whether an organization has this set for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="04c51-124">このパラメーターは、外部の参加者が、組織の会議のポリシーに設定されている内容に応じて、共有元の画面の制御を付与できるか、制御を要求するかを制御します。</span><span class="sxs-lookup"><span data-stu-id="04c51-124">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span>
    - <span data-ttu-id="04c51-125">**[PowerPoint 共有を許可する]**: ユーザーによる、PowerPoint プレゼンテーションのアップロードや共有ができる会議の作成を許可します。</span><span class="sxs-lookup"><span data-stu-id="04c51-125">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="04c51-126">**[ホワイトボードを許可する]**: ユーザーによるホワイトボードの共有を許可します。</span><span class="sxs-lookup"><span data-stu-id="04c51-126">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="04c51-127">**[共有メモを許可する]**: ユーザーが共有メモを取ることを許可します。</span><span class="sxs-lookup"><span data-stu-id="04c51-127">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="04c51-128">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04c51-128">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="04c51-129">PowerShell を使用して共有デスクトップを構成する</span><span class="sxs-lookup"><span data-stu-id="04c51-129">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="04c51-130">[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) コマンドレットを使用して、デスクトップ共有を制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="04c51-130">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="04c51-131">次のパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="04c51-131">Set the following parameters:</span></span>

- <span data-ttu-id="04c51-132">Description</span><span class="sxs-lookup"><span data-stu-id="04c51-132">Description</span></span>
- <span data-ttu-id="04c51-133">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="04c51-133">ScreenSharingMode</span></span>
- <span data-ttu-id="04c51-134">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="04c51-134">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="04c51-135">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="04c51-135">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="04c51-136">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="04c51-136">AllowPowerPointSharing</span></span>
- <span data-ttu-id="04c51-137">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="04c51-137">AllowWhiteboard</span></span>
- <span data-ttu-id="04c51-138">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="04c51-138">AllowSharedNotes</span></span>

<span data-ttu-id="04c51-139">[csTeamsMeetingPolicy コマンドレットの使用方法に関する詳細情報](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="04c51-139">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>

