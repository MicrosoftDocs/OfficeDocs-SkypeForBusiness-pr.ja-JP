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
description: Teams のチャットや会議でユーザーがデスクトップを共有できるように、会議ポリシーを構成します。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 99c6e2a5adb9d0f9a4b4e3f6f17b7484bda96a74
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2019
ms.locfileid: "37516888"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="8f459-103">Microsoft Teams でのデスクトップ共有を構成する</span><span class="sxs-lookup"><span data-stu-id="8f459-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="8f459-104">デスクトップを共有すると、ユーザーは会議やチャット中に画面やアプリを表示できます。</span><span class="sxs-lookup"><span data-stu-id="8f459-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="8f459-105">管理者が Microsoft Teams で画面共有を構成すると、ユーザーは画面全体、アプリ、ファイルを共有できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8f459-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="8f459-106">ユーザーによる制御の付与または要求の許可、PowerPoint 共有の許可、ホワイトボードの追加、共有メモの許可を設定できます。</span><span class="sxs-lookup"><span data-stu-id="8f459-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="8f459-107">匿名ユーザーや外部ユーザーが共有画面の制御を要求できるかどうかも構成できます。</span><span class="sxs-lookup"><span data-stu-id="8f459-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="8f459-108">画面共有を構成するには、新しい会議ポリシーを作成し、そのポリシーを管理対象ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8f459-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="8f459-109">**Microsoft Teams 管理センターで**</span><span class="sxs-lookup"><span data-stu-id="8f459-109">**In the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="8f459-110">**[会議]** > **[会議ポリシー]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="8f459-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![会議ポリシーが選択されていることを示すスクリーンショット](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="8f459-112">**[会議ポリシー]** ページで、**[新しいポリシー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f459-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![会議ポリシーのメッセージが表示されたスクリーンショット](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="8f459-114">ポリシーに一意のタイトルを指定し、簡単な説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="8f459-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="8f459-115">**[コンテンツの共有]** の下にある、**[画面共有モード]** ドロップダウン リストから選択します。</span><span class="sxs-lookup"><span data-stu-id="8f459-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="8f459-116">**[画面全体]**: ユーザーはデスクトップ全体を共有できます。</span><span class="sxs-lookup"><span data-stu-id="8f459-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="8f459-117">**[1 つのアプリケーション]**: ユーザーの画面共有は 1 つのアクティブなアプリケーションに制限されます。</span><span class="sxs-lookup"><span data-stu-id="8f459-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="8f459-118">**[無効]**: 画面共有をオフにします。</span><span class="sxs-lookup"><span data-stu-id="8f459-118">**Disabled** – Turns off screen sharing.</span></span>

    ![共有モードのオプションを示すスクリーンショット](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="8f459-120">次の設定をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="8f459-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="8f459-121">**[参加者による制御の付与または要求を許可する]**: チームのメンバーによる、発表者のデスクトップまたはアプリケーションの制御の付与や要求を許可します。</span><span class="sxs-lookup"><span data-stu-id="8f459-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="8f459-122">**[外部の参加者による制御の付与または要求を許可する]**: ゲストや外部の (フェデレーション) ユーザーによる、発表者のデスクトップまたはアプリケーションの制御の付与や要求を許可します。</span><span class="sxs-lookup"><span data-stu-id="8f459-122">**Allow an external participant to give or request control** – lets guests and external (federated) users give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="8f459-123">**[PowerPoint 共有を許可する]**: ユーザーによる、PowerPoint プレゼンテーションのアップロードや共有ができる会議の作成を許可します。</span><span class="sxs-lookup"><span data-stu-id="8f459-123">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="8f459-124">**[ホワイトボードを許可する]**: ユーザーによるホワイトボードの共有を許可します。</span><span class="sxs-lookup"><span data-stu-id="8f459-124">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="8f459-125">**[共有メモを許可する]**: ユーザーが共有メモを取ることを許可します。</span><span class="sxs-lookup"><span data-stu-id="8f459-125">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="8f459-126">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f459-126">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="8f459-127">PowerShell を使用して共有デスクトップを構成する</span><span class="sxs-lookup"><span data-stu-id="8f459-127">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="8f459-128">
  [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) コマンドレットを使用して、デスクトップ共有を制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="8f459-128">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="8f459-129">次のパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="8f459-129">Set the following parameters:</span></span>

- <span data-ttu-id="8f459-130">Description</span><span class="sxs-lookup"><span data-stu-id="8f459-130">Description</span></span>
- <span data-ttu-id="8f459-131">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="8f459-131">ScreenSharingMode</span></span>
- <span data-ttu-id="8f459-132">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="8f459-132">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="8f459-133">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="8f459-133">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="8f459-134">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="8f459-134">AllowPowerPointSharing</span></span>
- <span data-ttu-id="8f459-135">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="8f459-135">AllowWhiteboard</span></span>
- <span data-ttu-id="8f459-136">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="8f459-136">AllowSharedNotes</span></span>

<span data-ttu-id="8f459-137">
  [csTeamsMeetingPolicy コマンドレットの使用方法に関する詳細情報](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="8f459-137">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>

