---
title: 会議の設定を管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.meetingsettings.overview
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 組織内のユーザーのスケジュールを設定するチームの会議の設定を管理する方法について説明します。
ms.openlocfilehash: 4ded26dae69b5afef1d9fafb4819a73475c44898
ms.sourcegitcommit: 3000a661ac420eecd825a8285bdac7b744bd25da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "31959538"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a><span data-ttu-id="a625a-103">Microsoft Teams で会議の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="a625a-103">Manage meeting settings in Microsoft Teams</span></span>

<span data-ttu-id="a625a-104">管理者と匿名ユーザーは、チームの会議に参加、ミーティングの招待状をカスタマイズ、およびサービスの品質 (QoS) を有効にする場合は、リアルタイムのトラフィックをポート範囲を設定します。 かどうかチーム会議を制御する設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="a625a-104">As an admin, you use Teams meetings settings to control whether anonymous users can join Teams meetings, customize meeting invitations, and if you want to enable Quality of Service (QoS), set port ranges for real-time traffic.</span></span> <span data-ttu-id="a625a-105">これらの設定は、組織内でそのユーザーのスケジュールをチームのすべての会議に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a625a-105">These settings apply to all Teams meetings that users schedule in your organization.</span></span> <span data-ttu-id="a625a-106">**会議**からこれらの設定を管理する > マイクロソフト チームの管理センターでの**会議を設定**します。</span><span class="sxs-lookup"><span data-stu-id="a625a-106">You manage these settings from **Meetings** > **Meeting settings** in the Microsoft Teams admin center.</span></span>

## <a name="allow-anonymous-users-to-join-meetings"></a><span data-ttu-id="a625a-107">匿名ユーザーが会議に参加できるように</span><span class="sxs-lookup"><span data-stu-id="a625a-107">Allow anonymous users to join meetings</span></span>

<span data-ttu-id="a625a-108">匿名結合は、ミーティング招待状のリンクをクリックすると、匿名ユーザーとして会議に参加誰でもできます。</span><span class="sxs-lookup"><span data-stu-id="a625a-108">With anonymous join, anyone can join the meeting as an anonymous user by clicking the link in the meeting invitation.</span></span>

<span data-ttu-id="a625a-109">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**</span><span class="sxs-lookup"><span data-stu-id="a625a-109">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="a625a-110">左側のナビゲーションでは、**会議**に移動 > **会議を設定**します。</span><span class="sxs-lookup"><span data-stu-id="a625a-110">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
2. <span data-ttu-id="a625a-111">**参加者**の下でオンに**匿名ユーザーが会議に参加できます**。</span><span class="sxs-lookup"><span data-stu-id="a625a-111">Under **Participants**, turn on **Anonymous users can join a meeting**.</span></span>

    <span data-ttu-id="a625a-112">![会議の設定-participants.png](media/meeting-settings-participants.png "マイクロソフトのチームの管理センターでのチーム会議の参加者の設定のスクリーン ショット")</span><span class="sxs-lookup"><span data-stu-id="a625a-112">![meeting-settings-participants.png](media/meeting-settings-participants.png "Screen shot of participants settings for Teams meetings in the Microsoft Teams admin center")</span></span>

<span data-ttu-id="a625a-113">匿名ユーザーは、組織内のユーザーがスケジュールしたミーティングに参加しない場合は、この設定をオフにします。</span><span class="sxs-lookup"><span data-stu-id="a625a-113">If you don't want anonymous users to join meetings scheduled by users in your organization, turn off this setting.</span></span>

## <a name="customize-meeting-invitations"></a><span data-ttu-id="a625a-114">会議出席依頼をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="a625a-114">Customize meeting invitations</span></span>

<span data-ttu-id="a625a-115">組織のニーズを満たすためにチームのミーティングの招待状をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="a625a-115">You can customize Teams meeting invitations to meet your organization's needs.</span></span> <span data-ttu-id="a625a-116">組織のロゴを追加したり、サポート用 web サイトと免責事項、およびテキストのみのフッターへのリンクなど、役に立つ情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a625a-116">You can add your organization's logo and include helpful information, such as links to your support website and legal disclaimer, and a text-only footer.</span></span>

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a><span data-ttu-id="a625a-117">会議出席依頼のロゴを作成するためのヒント</span><span class="sxs-lookup"><span data-stu-id="a625a-117">Tips for creating a logo for meeting invitations</span></span>  

1. <span data-ttu-id="a625a-118">188 ピクセル 30 ピクセルの高さ (非常に小さいです) では、イメージを作成します。</span><span class="sxs-lookup"><span data-stu-id="a625a-118">Create an image that's no more than 188 pixels wide by 30 pixels tall (it's quite small).</span></span>
2. <span data-ttu-id="a625a-119">イメージを JPG 形式で保存します。</span><span class="sxs-lookup"><span data-stu-id="a625a-119">Save the image in JPG format.</span></span>
3. <span data-ttu-id="a625a-120">ネットワーク共有など、組織内のすべてのユーザーがアクセスできる中央の場所にイメージを格納します。</span><span class="sxs-lookup"><span data-stu-id="a625a-120">Store the image in a central location that everyone in your organization can access, such as a network share.</span></span>

### <a name="customize-your-meeting-invitations"></a><span data-ttu-id="a625a-121">会議出席依頼をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="a625a-121">Customize your meeting invitations</span></span>

<span data-ttu-id="a625a-122">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**</span><span class="sxs-lookup"><span data-stu-id="a625a-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="a625a-123">左側のナビゲーションでは、**会議**に移動 > **会議を設定**します。</span><span class="sxs-lookup"><span data-stu-id="a625a-123">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
2. <span data-ttu-id="a625a-124">[**電子メール招待状**の場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a625a-124">Under **Email invitation**, do the following:</span></span>

    <span data-ttu-id="a625a-125">![会議の設定-invitation.png](media/meeting-settings-invitation.png "のスクリーン ショットは、会議のチーム会議用にカスタマイズできる招待状の設定")</span><span class="sxs-lookup"><span data-stu-id="a625a-125">![meeting-settings-invitation.png](media/meeting-settings-invitation.png "Screen shot of the meeting invitation settings that you can customize for Teams meetings")</span></span>

    - <span data-ttu-id="a625a-126">**ロゴの URL**ロゴを保存する場所の URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="a625a-126">**Logo URL** Enter the URL where your logo is stored.</span></span>
    - <span data-ttu-id="a625a-127">**有効な URL**組織の法的な懸念事項を参照する有効な web サイトの場合は、ここに URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="a625a-127">**Legal URL** If your organization has a legal website that you want people to go to for any legal concerns, enter the URL here.</span></span>
    - <span data-ttu-id="a625a-128">**URL のヘルプ**組織がサポートする web サイトに問題が発生する場合に移動するようにする場合は、ここに URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="a625a-128">**Help URL** If your organization has a support website that you want people to go to if they run into issues, enter the URL here.</span></span>
    - <span data-ttu-id="a625a-129">**フッター**フッターとして使用するテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="a625a-129">**Footer** Enter text that you want to include as a footer.</span></span>
3. <span data-ttu-id="a625a-130">1 時間など、変更を伝達するを待ちます。</span><span class="sxs-lookup"><span data-stu-id="a625a-130">Wait an hour or so for the changes to propagate.</span></span> <span data-ttu-id="a625a-131">会議のチームに会議出席依頼は次のように参照してください。</span><span class="sxs-lookup"><span data-stu-id="a625a-131">Then schedule a Teams meeting to see what the meeting invitation looks like.</span></span>  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a><span data-ttu-id="a625a-132">チームの会議のためのリアルタイムのメディア トラフィックを処理する方法を設定します。</span><span class="sxs-lookup"><span data-stu-id="a625a-132">Set how you want to handle real-time media traffic for Teams meetings</span></span>

<span data-ttu-id="a625a-133"><a name="bknetwork"> </a></span><span class="sxs-lookup"><span data-stu-id="a625a-133"></span></span>

<span data-ttu-id="a625a-134">ネットワーク トラフィックの優先順位を設定するのにはサービスの品質[(QoS)](qos-in-teams.md)を使用する場合は、QoS のマーカーを有効にすることができ、メディア トラフィックの種類ごとにポートの範囲を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="a625a-134">If you're using Quality of Service [(QoS)](qos-in-teams.md) to prioritize network traffic, you can enable QoS markers and you can set port ranges for each type of media traffic.</span></span>

 <span data-ttu-id="a625a-135">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**</span><span class="sxs-lookup"><span data-stu-id="a625a-135">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="a625a-136">左側のナビゲーションでは、**会議**に移動 > **会議を設定**します。</span><span class="sxs-lookup"><span data-stu-id="a625a-136">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
2. <span data-ttu-id="a625a-137">[**ネットワーク**では、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a625a-137">Under **Network**, do the following:</span></span>

    <span data-ttu-id="a625a-138">![会議の設定-network.png](media/meeting-settings-network.png "チーム会議は、マイクロソフトのチームの管理センターでのネットワーク設定のスクリーン ショット")</span><span class="sxs-lookup"><span data-stu-id="a625a-138">![meeting-settings-network.png](media/meeting-settings-network.png "Screen shot of the network settings for Teams meetings in the Microsoft Teams admin center")</span></span>

    - <span data-ttu-id="a625a-139">QoS を使用する DSCP マーキングを許可するには、**トラフィックのリアルタイム メディアの挿入のサービスの品質 (QoS) のマーカー**を入れます。</span><span class="sxs-lookup"><span data-stu-id="a625a-139">To allow DSCP markings to be used for QoS, turn on **Insert Quality of Service (QoS) markers for real-time media traffic**.</span></span> <span data-ttu-id="a625a-140">どうか、マーカーを使用するオプションだけがあります。トラフィックの種類ごとにカスタム マーカーを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="a625a-140">You only have the option of using markers or not; you can't set custom markers for each traffic type.</span></span> <span data-ttu-id="a625a-141">DSCP マーカーが複数の[QoS の実装方法を選択する](QoS-in-Teams.md#select-a-qos-implementation-method)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a625a-141">See [Select a QoS implementation method](QoS-in-Teams.md#select-a-qos-implementation-method) for more on DSCP markers.</span></span>
    - <span data-ttu-id="a625a-142">**リアルタイム メディア トラフィックの種類ごとにポートの範囲を選択**すると、横には、ポート範囲を指定するのには**を指定するポートの範囲**を選択し、オーディオ、ビデオ、および画面共有の開始と終了のポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="a625a-142">To specify port ranges, next to **Select a port range for each type of real-time media traffic**, select  **Specify port ranges**, and then enter the starting and ending ports for audio, video, and screen sharing.</span></span> <span data-ttu-id="a625a-143">このオプションを選択すると、QoS を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a625a-143">Selecting this option is required to implement QoS.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="a625a-144">**自動的にすべての利用可能なポートを使用して**1024 の間で利用可能なポートを選択すると、65535 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a625a-144">If you select **Automatically use any available ports**, available ports between 1024 and 65535 are used.</span></span> <span data-ttu-id="a625a-145">QoS を実装しない場合にのみ、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="a625a-145">Use this option only when not implementing QoS.</span></span>
    >
    > <span data-ttu-id="a625a-146">ポートの範囲が狭すぎることを選択することにより、通話の中断や品質の低い呼び出しされます。</span><span class="sxs-lookup"><span data-stu-id="a625a-146">Selecting a port range that is too narrow will lead to dropped calls and poor call quality.</span></span> <span data-ttu-id="a625a-147">以下の推奨事項には、最小限に抑える必要があります。</span><span class="sxs-lookup"><span data-stu-id="a625a-147">The recommendations below should be a bare minimum.</span></span>

 <span data-ttu-id="a625a-148">明確でない環境で使用するポートの範囲は、次の設定は、開始点をしてください。</span><span class="sxs-lookup"><span data-stu-id="a625a-148">If you are unsure what port ranges to use in your environment, the following settings are a good starting point.</span></span> <span data-ttu-id="a625a-149">詳細については、[実装のサービス品質 (QoS) では、マイクロソフトのチーム](QoS-in-Teams.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a625a-149">To learn more, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span> <span data-ttu-id="a625a-150">これらは、必須の DSCP マーキングと推奨される対応するメディア チームと ExpressRoute の両方で使用する範囲のポートです。</span><span class="sxs-lookup"><span data-stu-id="a625a-150">These are the required DSCP markings and the suggested corresponding media port ranges used by both Teams and ExpressRoute.</span></span>

<span data-ttu-id="a625a-151">_ポート範囲および DSCP マーキング_</span><span class="sxs-lookup"><span data-stu-id="a625a-151">_Port ranges and DSCP markings_</span></span>

<span data-ttu-id="a625a-152">メディア トラフィックの種類</span><span class="sxs-lookup"><span data-stu-id="a625a-152">Media traffic type</span></span>| <span data-ttu-id="a625a-153">クライアント ソース ポートの範囲\*</span><span class="sxs-lookup"><span data-stu-id="a625a-153">Client source port range \*</span></span> |<span data-ttu-id="a625a-154">プロトコル</span><span class="sxs-lookup"><span data-stu-id="a625a-154">Protocol</span></span>|<span data-ttu-id="a625a-155">DSCP 値</span><span class="sxs-lookup"><span data-stu-id="a625a-155">DSCP value</span></span>|<span data-ttu-id="a625a-156">DSCP クラス</span><span class="sxs-lookup"><span data-stu-id="a625a-156">DSCP class</span></span>|
|:---             |:---                         |:---    |:---      |:---      |
|<span data-ttu-id="a625a-157">オーディオ</span><span class="sxs-lookup"><span data-stu-id="a625a-157">Audio</span></span>            | <span data-ttu-id="a625a-158">50,000 – 50,019</span><span class="sxs-lookup"><span data-stu-id="a625a-158">50,000–50,019</span></span>               |<span data-ttu-id="a625a-159">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="a625a-159">TCP/UDP</span></span> |<span data-ttu-id="a625a-160">46</span><span class="sxs-lookup"><span data-stu-id="a625a-160">46</span></span>        |<span data-ttu-id="a625a-161">完全優先転送 (EF)</span><span class="sxs-lookup"><span data-stu-id="a625a-161">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="a625a-162">ビデオ</span><span class="sxs-lookup"><span data-stu-id="a625a-162">Video</span></span>            | <span data-ttu-id="a625a-163">50,020 – 50,039</span><span class="sxs-lookup"><span data-stu-id="a625a-163">50,020–50,039</span></span>               |<span data-ttu-id="a625a-164">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="a625a-164">TCP/UDP</span></span> |<span data-ttu-id="a625a-165">34</span><span class="sxs-lookup"><span data-stu-id="a625a-165">34</span></span>        |<span data-ttu-id="a625a-166">相対的優先転送 (AF41)</span><span class="sxs-lookup"><span data-stu-id="a625a-166">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="a625a-167">アプリケーションと画面の共有</span><span class="sxs-lookup"><span data-stu-id="a625a-167">Application/Screen Sharing</span></span>| <span data-ttu-id="a625a-168">50,040-50,059</span><span class="sxs-lookup"><span data-stu-id="a625a-168">50,040–50,059</span></span>      |<span data-ttu-id="a625a-169">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="a625a-169">TCP/UDP</span></span> |<span data-ttu-id="a625a-170">18</span><span class="sxs-lookup"><span data-stu-id="a625a-170">18</span></span>        |<span data-ttu-id="a625a-171">相対的優先転送 (AF21)</span><span class="sxs-lookup"><span data-stu-id="a625a-171">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="a625a-172">\*割り当てるポートの範囲は、重ねることはできませんし、互いに隣接する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a625a-172">\* The port ranges you assign cannot overlap and must be adjacent to each other.</span></span>

<span data-ttu-id="a625a-173">リアルタイム メディアを処理するときの 1 つのステップは、種類の異なるトラフィックのポート範囲を設定します。詳細な[サービスの品質 (QoS)](qos-in-teams.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a625a-173">Setting port ranges for different traffic types is only one step in handling real time media; see [Quality of Service (QoS) in Teams](qos-in-teams.md) for much more detail.</span></span> <span data-ttu-id="a625a-174">有効にするか、マイクロソフトのチーム管理センターの設定を変更した場合は、チームでの QoS への変更を完全に実装する[すべてのユーザーのデバイスに一致する設定を適用](QoS-in-Teams-clients.md)し、内部のネットワーク デバイスに必要があります。</span><span class="sxs-lookup"><span data-stu-id="a625a-174">If you enable or change settings in the Microsoft Teams admin center, you will need to [apply matching settings to all user devices](QoS-in-Teams-clients.md) and internal network devices to fully implement the changes to QoS in Teams.</span></span>

<span data-ttu-id="a625a-175">QoS が使用された後、しばらくの間、これら 3 つのワークロードごとに、オン ・ デマンドでの使用状況に関する情報があり、どのような変更を加えるに基づいて、特定のニーズを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="a625a-175">After QoS has been in use for a while, you'll have usage information on the demand for each of these three workloads, and you can choose what changes to make based on your specific needs.</span></span> <span data-ttu-id="a625a-176">[品質のダッシュ ボードを呼び出す](turning-on-and-using-call-quality-dashboard.md)と便利になります。</span><span class="sxs-lookup"><span data-stu-id="a625a-176">[Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md) will be helpful with that.</span></span>
