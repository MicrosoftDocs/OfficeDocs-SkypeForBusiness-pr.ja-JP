---
title: Microsoft Teams でのデスクトップ共有を構成する
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
description: ユーザーがチャットや会議でデスクトップを共有Teams構成する方法について学習します。
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 56ee2c83827c25da5b16cc3f7c2725a3daf815c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121515"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="20049-103">Microsoft Teams でのデスクトップ共有を構成する</span><span class="sxs-lookup"><span data-stu-id="20049-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="20049-104">デスクトップを共有すると、ユーザーは会議やチャット中に画面やアプリを表示できます。</span><span class="sxs-lookup"><span data-stu-id="20049-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="20049-105">管理者が Microsoft Teams で画面共有を構成すると、ユーザーは画面全体、アプリ、ファイルを共有できるようになります。</span><span class="sxs-lookup"><span data-stu-id="20049-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="20049-106">ユーザーによる制御の付与または要求の許可、PowerPoint 共有の許可、ホワイトボードの追加、共有メモの許可を設定できます。</span><span class="sxs-lookup"><span data-stu-id="20049-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="20049-107">匿名ユーザーや外部ユーザーが共有画面の制御を要求できるかどうかも構成できます。</span><span class="sxs-lookup"><span data-stu-id="20049-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span> <span data-ttu-id="20049-108">Teams 会議の外部参加者は、次のように分類できます。</span><span class="sxs-lookup"><span data-stu-id="20049-108">External participants in Teams meetings can be categorized as follows:</span></span>

- <span data-ttu-id="20049-109">匿名ユーザー</span><span class="sxs-lookup"><span data-stu-id="20049-109">Anonymous user</span></span>
- <span data-ttu-id="20049-110">ゲスト ユーザー</span><span class="sxs-lookup"><span data-stu-id="20049-110">Guest users</span></span>
- <span data-ttu-id="20049-111">B2B ユーザー</span><span class="sxs-lookup"><span data-stu-id="20049-111">B2B user</span></span>
- <span data-ttu-id="20049-112">フェデレーション ユーザー</span><span class="sxs-lookup"><span data-stu-id="20049-112">Federated user</span></span>

<span data-ttu-id="20049-113">画面共有を構成するには、新しい会議ポリシーを作成し、そのポリシーを管理対象ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="20049-113">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="20049-114">**[Microsoft Teams 管理センター](https://admin.teams.microsoft.com/)で**</span><span class="sxs-lookup"><span data-stu-id="20049-114">**In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/)**</span></span>

1. <span data-ttu-id="20049-115">**[会議]** > **[会議ポリシー]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="20049-115">Select **Meetings** > **Meeting policies**.</span></span>

    ![会議ポリシーが選択されている](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="20049-117">[会議ポリシー **] ページで、[** 追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="20049-117">On the **Meeting policies** page, select **Add**.</span></span>

    ![[会議ポリシー] メッセージ](media/addMeeting.png)

3. <span data-ttu-id="20049-119">ポリシーに一意のタイトルを指定し、簡単な説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="20049-119">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="20049-120">**[コンテンツの共有]** の下にある、**[画面共有モード]** ドロップダウン リストから選択します。</span><span class="sxs-lookup"><span data-stu-id="20049-120">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="20049-121">**[画面全体]**: ユーザーはデスクトップ全体を共有できます。</span><span class="sxs-lookup"><span data-stu-id="20049-121">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="20049-122">**[1 つのアプリケーション]**: ユーザーの画面共有は 1 つのアクティブなアプリケーションに制限されます。</span><span class="sxs-lookup"><span data-stu-id="20049-122">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="20049-123">**[無効]**: 画面共有をオフにします。</span><span class="sxs-lookup"><span data-stu-id="20049-123">**Disabled** – Turns off screen sharing.</span></span>

    ![共有モードのオプション](media/configure-desktop-sharing-image3.png)

  > [!Note]
  > <span data-ttu-id="20049-125">ユーザーがチャットから画面共有を使用するために、呼び出し元ポリシーを有効にする必要はない。</span><span class="sxs-lookup"><span data-stu-id="20049-125">You don't have to enable the calling policy in order for users to use screen share from chat.</span></span> <span data-ttu-id="20049-126">ただし、ミュートを解除するまで、オーディオはオフになります。</span><span class="sxs-lookup"><span data-stu-id="20049-126">However, their audio is turned off until they unmute themselves.</span></span> <span data-ttu-id="20049-127">さらに、画面を共有しているユーザーは、[オーディオの追加] **をクリックして** オーディオを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="20049-127">In addition, the user sharing the screen can click **Add Audio** to enable audio.</span></span> <span data-ttu-id="20049-128">呼び出し元ポリシーが無効になっている場合、ユーザーはチャット セッションから画面共有にオーディオを追加できません。</span><span class="sxs-lookup"><span data-stu-id="20049-128">If the calling policy is disabled, users won't be able to add audio to the screen share from a chat session.</span></span>

5. <span data-ttu-id="20049-129">次の設定をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="20049-129">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="20049-130">**参加者に制御の許可または** 要求を許可する - チームのメンバーが発表者のデスクトップまたはアプリケーションの制御を許可または要求できます。</span><span class="sxs-lookup"><span data-stu-id="20049-130">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter's desktop or application.</span></span>
    - <span data-ttu-id="20049-131">**外部参加者に制御の許可または要求を許可** する – これはユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="20049-131">**Allow an external participant to give or request control** – This is a per-user policy.</span></span> <span data-ttu-id="20049-132">組織がユーザーに対してこの設定を行ったかどうかは、会議の開催者が設定した内容に関係なく、外部の参加者ができることを制御するものではありません。</span><span class="sxs-lookup"><span data-stu-id="20049-132">Whether an organization has this set for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="20049-133">このパラメーターは、組織の会議ポリシー内において、共有先が設定した内容に応じて、外部の参加者に共有スクリーンの制御または制御の依頼を許可するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="20049-133">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span>
    - <span data-ttu-id="20049-134">**[PowerPoint 共有を許可する]**: ユーザーによる、PowerPoint プレゼンテーションのアップロードや共有ができる会議の作成を許可します。</span><span class="sxs-lookup"><span data-stu-id="20049-134">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="20049-135">**[ホワイトボードを許可する]**: ユーザーによるホワイトボードの共有を許可します。</span><span class="sxs-lookup"><span data-stu-id="20049-135">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="20049-136">**[共有メモを許可する]**: ユーザーが共有メモを取ることを許可します。</span><span class="sxs-lookup"><span data-stu-id="20049-136">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="20049-137">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20049-137">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="20049-138">PowerShell を使用して共有デスクトップを構成する</span><span class="sxs-lookup"><span data-stu-id="20049-138">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="20049-139">[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) コマンドレットを使用して、デスクトップ共有を制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="20049-139">You can also use the [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="20049-140">次のパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="20049-140">Set the following parameters:</span></span>

- <span data-ttu-id="20049-141">Description</span><span class="sxs-lookup"><span data-stu-id="20049-141">Description</span></span>
- <span data-ttu-id="20049-142">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="20049-142">ScreenSharingMode</span></span>
- <span data-ttu-id="20049-143">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="20049-143">AllowPrivateCalling</span></span>
- <span data-ttu-id="20049-144">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="20049-144">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="20049-145">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="20049-145">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="20049-146">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="20049-146">AllowPowerPointSharing</span></span>
- <span data-ttu-id="20049-147">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="20049-147">AllowWhiteboard</span></span>
- <span data-ttu-id="20049-148">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="20049-148">AllowSharedNotes</span></span>

<span data-ttu-id="20049-149">[csTeamsMeetingPolicy コマンドレットの使用方法に関する詳細情報](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="20049-149">[Learn more about using the csTeamsMeetingPolicy cmdlet](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>