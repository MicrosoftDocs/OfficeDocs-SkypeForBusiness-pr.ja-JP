---
title: マイクロソフトのチームでデスクトップの共有を構成します。
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 12/07/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: チーム チャットや会議での自分のデスクトップを共有できるようにするのには会議ポリシーを構成します。
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 422d5fb3a19dad2e14e0cdf54a532b0afc6eed67
ms.sourcegitcommit: ea6ee8ce28e82fcd7c07554c3428ae242d6f04da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/07/2018
ms.locfileid: "27202506"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="dc1a3-103">マイクロソフトのチームでデスクトップの共有を構成します。</span><span class="sxs-lookup"><span data-stu-id="dc1a3-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="dc1a3-104">デスクトップの共有には、ユーザーが会議出席依頼やチャット中に、画面またはアプリケーションを提示することができます。</span><span class="sxs-lookup"><span data-stu-id="dc1a3-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="dc1a3-105">管理者は、画面を画面全体、アプリケーション、またはファイルを共有できるようにするのには、マイクロソフトのチームで共有を構成できます。</span><span class="sxs-lookup"><span data-stu-id="dc1a3-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="dc1a3-106">ユーザーを与える制御を要求、PowerPoint の共有を許可する、ホワイト ボードの追加やノートの共有を許可することもできます。</span><span class="sxs-lookup"><span data-stu-id="dc1a3-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="dc1a3-107">匿名または外部のユーザーが共有画面のコントロールを要求できるかどうかを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="dc1a3-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="dc1a3-108">画面共有を構成するには、新しい会議ポリシーを作成し、管理するユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="dc1a3-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="dc1a3-109">マイクロソフトのチームとビジネス管理センターの Skype。</span><span class="sxs-lookup"><span data-stu-id="dc1a3-109">In the Microsoft Teams & Skype for Business Admin Center:</span></span>

1. <span data-ttu-id="dc1a3-110">**会議**を選択して > **ミーティングのポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="dc1a3-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![ミーティングのポリシーを選択します。](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="dc1a3-112">[**ミーティングのポリシー** ] ページで、**新しいポリシー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc1a3-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![新しいポリシーを選択します。](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="dc1a3-114">ポリシー固有のタイトルを提供し、簡単な説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="dc1a3-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="dc1a3-115">**コンテンツの共有**の下にあるドロップ ダウン リストから**画面共有モード**を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc1a3-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="dc1a3-116">**全体画面**– を使うと、その全体のデスクトップを共有できます。</span><span class="sxs-lookup"><span data-stu-id="dc1a3-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="dc1a3-117">**1 つのアプリケーション**では、1 つのアクティブなアプリケーションを制限画面の共有をユーザーことができます。</span><span class="sxs-lookup"><span data-stu-id="dc1a3-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="dc1a3-118">**無効**– 画面の共有を無効にします。</span><span class="sxs-lookup"><span data-stu-id="dc1a3-118">**Disabled** – Turns off screen sharing.</span></span>

    ![共有モードの画面を選択します。](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="dc1a3-120">次の設定を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="dc1a3-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="dc1a3-121">提供または、発表者のデスクトップまたはアプリケーションの制御を要求**したり制御を要求する参加者を許可する**: チームのメンバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc1a3-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="dc1a3-122">来園者は、**制御を要求したりする外部の参加者を許可する**- と (連合) の外部のユーザーが付与または、発表者のデスクトップまたはアプリケーションの制御を要求します。</span><span class="sxs-lookup"><span data-stu-id="dc1a3-122">**Allow an external participant to give or request control** – lets guests and external (federated) users give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="dc1a3-123">**PowerPoint の共有**- には、ユーザーが PowerPoint のプレゼンテーションをアップロードして共有できるように会議を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="dc1a3-123">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="dc1a3-124">**許可するホワイト ボード**-では、ホワイト ボードを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="dc1a3-124">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="dc1a3-125">**ノートの共有を許可する**-には、ユーザーが共有ノートを取ることができます。</span><span class="sxs-lookup"><span data-stu-id="dc1a3-125">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="dc1a3-126">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc1a3-126">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="dc1a3-127">PowerShell を使用して、デスクトップの共有を構成するには</span><span class="sxs-lookup"><span data-stu-id="dc1a3-127">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="dc1a3-128">デスクトップの共有を制御する[セット CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)コマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="dc1a3-128">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="dc1a3-129">次のパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="dc1a3-129">Set the following parameters:</span></span>

- <span data-ttu-id="dc1a3-130">説明</span><span class="sxs-lookup"><span data-stu-id="dc1a3-130">Description</span></span>
- <span data-ttu-id="dc1a3-131">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="dc1a3-131">ScreenSharingMode</span></span>
- <span data-ttu-id="dc1a3-132">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="dc1a3-132">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="dc1a3-133">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="dc1a3-133">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="dc1a3-134">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="dc1a3-134">AllowPowerPointSharing</span></span>
- <span data-ttu-id="dc1a3-135">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="dc1a3-135">AllowWhiteboard</span></span>
- <span data-ttu-id="dc1a3-136">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="dc1a3-136">AllowSharedNotes</span></span>

<span data-ttu-id="dc1a3-137">[CsTeamsMeetingPolicy コマンドレットを使用してに関する詳細を表示](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)します。</span><span class="sxs-lookup"><span data-stu-id="dc1a3-137">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>

