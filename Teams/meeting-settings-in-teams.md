---
title: 会議の設定を管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.meetingsettings.overview
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 組織でスケジュールされているユーザーのチーム会議の設定を管理する方法について説明します。
ms.openlocfilehash: 9dab34c518b4c0c5c25e55d894a1dacf4e0a773e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298120"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a><span data-ttu-id="70110-103">Microsoft Teams で会議の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="70110-103">Manage meeting settings in Microsoft Teams</span></span>

<span data-ttu-id="70110-104">管理者として、Teams 会議の設定を使用して、匿名ユーザーが Teams 会議に参加できるかどうかを制御したり、会議出席依頼をカスタマイズしたり、サービスの品質 (QoS) を有効にしたりする場合は、リアルタイムトラフィック用のポート範囲を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70110-104">As an admin, you use Teams meetings settings to control whether anonymous users can join Teams meetings, customize meeting invitations, and if you want to enable Quality of Service (QoS), set port ranges for real-time traffic.</span></span> <span data-ttu-id="70110-105">これらの設定は、ユーザーが組織でスケジュールしたすべてのチーム会議に適用されます。</span><span class="sxs-lookup"><span data-stu-id="70110-105">These settings apply to all Teams meetings that users schedule in your organization.</span></span> <span data-ttu-id="70110-106">これらの設定は、Microsoft Teams 管理センターの**会議** > の**設定**から管理します。</span><span class="sxs-lookup"><span data-stu-id="70110-106">You manage these settings from **Meetings** > **Meeting settings** in the Microsoft Teams admin center.</span></span>

## <a name="allow-anonymous-users-to-join-meetings"></a><span data-ttu-id="70110-107">匿名ユーザーによる会議への参加を許可する</span><span class="sxs-lookup"><span data-stu-id="70110-107">Allow anonymous users to join meetings</span></span>

<span data-ttu-id="70110-108">匿名の参加では、会議出席依頼のリンクをクリックすると、誰でも匿名ユーザーとして会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="70110-108">With anonymous join, anyone can join the meeting as an anonymous user by clicking the link in the meeting invitation.</span></span>

<span data-ttu-id="70110-109">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="70110-109">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="70110-110">左側のナビゲーションで、[**会議** > の**会議の設定**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="70110-110">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
2. <span data-ttu-id="70110-111">[**参加者**] の下で、[**匿名ユーザーが会議に参加できるよう**にする] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="70110-111">Under **Participants**, turn on **Anonymous users can join a meeting**.</span></span>

    <span data-ttu-id="70110-112">![meeting-settings-participants](media/meeting-settings-participants.png "Microsoft teams 管理センターでの Teams 会議の参加者設定のスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="70110-112">![meeting-settings-participants.png](media/meeting-settings-participants.png "Screen shot of participants settings for Teams meetings in the Microsoft Teams admin center")</span></span>

<span data-ttu-id="70110-113">組織内のユーザーによってスケジュールされている会議に匿名ユーザーが会議に参加しないようにするには、この設定をオフにします。</span><span class="sxs-lookup"><span data-stu-id="70110-113">If you don't want anonymous users to join meetings scheduled by users in your organization, turn off this setting.</span></span>

## <a name="customize-meeting-invitations"></a><span data-ttu-id="70110-114">会議の出席依頼をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="70110-114">Customize meeting invitations</span></span>

<span data-ttu-id="70110-115">組織のニーズに合わせて、Teams の会議出席依頼をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="70110-115">You can customize Teams meeting invitations to meet your organization's needs.</span></span> <span data-ttu-id="70110-116">組織のロゴを追加したり、サポート web サイトや法的免責事項へのリンクやテキストのみのフッターなど、有用な情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="70110-116">You can add your organization's logo and include helpful information, such as links to your support website and legal disclaimer, and a text-only footer.</span></span>

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a><span data-ttu-id="70110-117">会議出席依頼のロゴを作成するためのヒント</span><span class="sxs-lookup"><span data-stu-id="70110-117">Tips for creating a logo for meeting invitations</span></span>  

1. <span data-ttu-id="70110-118">高さが188ピクセル未満で、幅が30ピクセル以下の画像を作成します (非常に小さい)。</span><span class="sxs-lookup"><span data-stu-id="70110-118">Create an image that's no more than 188 pixels wide by 30 pixels tall (it's quite small).</span></span>
2. <span data-ttu-id="70110-119">イメージを JPG 形式で保存します。</span><span class="sxs-lookup"><span data-stu-id="70110-119">Save the image in JPG format.</span></span>
3. <span data-ttu-id="70110-120">ネットワーク共有など、組織内のすべてのユーザーがアクセスできる一元的な場所に画像を保存します。</span><span class="sxs-lookup"><span data-stu-id="70110-120">Store the image in a central location that everyone in your organization can access, such as a network share.</span></span>

### <a name="customize-your-meeting-invitations"></a><span data-ttu-id="70110-121">会議出席依頼をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="70110-121">Customize your meeting invitations</span></span>

<span data-ttu-id="70110-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="70110-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="70110-123">左側のナビゲーションで、[**会議** > の**会議の設定**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="70110-123">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
2. <span data-ttu-id="70110-124">[**電子メールの招待状**] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="70110-124">Under **Email invitation**, do the following:</span></span>

    <span data-ttu-id="70110-125">![meeting-settings-invitation](media/meeting-settings-invitation.png "チーム会議用にカスタマイズできる会議出席依頼の設定のスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="70110-125">![meeting-settings-invitation.png](media/meeting-settings-invitation.png "Screen shot of the meeting invitation settings that you can customize for Teams meetings")</span></span>

    - <span data-ttu-id="70110-126">**ロゴ URL**ロゴが保存されている URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="70110-126">**Logo URL** Enter the URL where your logo is stored.</span></span>
    - <span data-ttu-id="70110-127">**法的**情報の URL法的な懸念事項についてユーザーに連絡する法的 web サイトが組織にある場合は、URL をここに入力します。</span><span class="sxs-lookup"><span data-stu-id="70110-127">**Legal URL** If your organization has a legal website that you want people to go to for any legal concerns, enter the URL here.</span></span>
    - <span data-ttu-id="70110-128">**ヘルプ URL**問題が発生した場合にユーザーが移動できるサポート web サイトが組織にある場合は、URL をここに入力します。</span><span class="sxs-lookup"><span data-stu-id="70110-128">**Help URL** If your organization has a support website that you want people to go to if they run into issues, enter the URL here.</span></span>
    - <span data-ttu-id="70110-129">**フッター**フッターとして追加するテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="70110-129">**Footer** Enter text that you want to include as a footer.</span></span>
3. <span data-ttu-id="70110-130">変更を反映させるには1時間ほど待ちます。</span><span class="sxs-lookup"><span data-stu-id="70110-130">Wait an hour or so for the changes to propagate.</span></span> <span data-ttu-id="70110-131">次に、Teams 会議をスケジュールして、会議の出席依頼がどのように表示されるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="70110-131">Then schedule a Teams meeting to see what the meeting invitation looks like.</span></span>  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a><span data-ttu-id="70110-132">Teams 会議でのリアルタイムのメディアトラフィックの処理方法を設定する</span><span class="sxs-lookup"><span data-stu-id="70110-132">Set how you want to handle real-time media traffic for Teams meetings</span></span>

<span data-ttu-id="70110-133"><a name="bknetwork"> </a></span><span class="sxs-lookup"><span data-stu-id="70110-133"></span></span>

<span data-ttu-id="70110-134">Qos (Quality of Service [)](qos-in-teams.md)を使ってネットワークトラフィックの優先順位を設定している場合は、qos マーカーを有効にして、メディアトラフィックごとにポート範囲を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="70110-134">If you're using Quality of Service [(QoS)](qos-in-teams.md) to prioritize network traffic, you can enable QoS markers and you can set port ranges for each type of media traffic.</span></span>

 <span data-ttu-id="70110-135">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="70110-135">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="70110-136">左側のナビゲーションで、[**会議** > の**会議の設定**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="70110-136">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
2. <span data-ttu-id="70110-137">[**ネットワーク**] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="70110-137">Under **Network**, do the following:</span></span>

    <span data-ttu-id="70110-138">![meeting-settings-network](media/meeting-settings-network.png "Microsoft teams 管理センターの teams 会議のネットワーク設定のスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="70110-138">![meeting-settings-network.png](media/meeting-settings-network.png "Screen shot of the network settings for Teams meetings in the Microsoft Teams admin center")</span></span>

    - <span data-ttu-id="70110-139">QoS に DSCP マーキングを使用できるようにするには、**リアルタイムメディアトラフィックの [サービス品質 (QoS) マーカーの挿入**] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="70110-139">To allow DSCP markings to be used for QoS, turn on **Insert Quality of Service (QoS) markers for real-time media traffic**.</span></span> <span data-ttu-id="70110-140">マーカーを使用するかどうかは選択できません。トラフィックの種類ごとにカスタムマーカーを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="70110-140">You only have the option of using markers or not; you can't set custom markers for each traffic type.</span></span> <span data-ttu-id="70110-141">詳細については[、「QoS の実装方法を選択する](QoS-in-Teams.md#select-a-qos-implementation-method)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70110-141">See [Select a QoS implementation method](QoS-in-Teams.md#select-a-qos-implementation-method) for more on DSCP markers.</span></span>
    - <span data-ttu-id="70110-142">ポート範囲を指定するには\*\*\*\*、[ポート範囲の指定] の横にある [ポート範囲の**指定**] を選択し、オーディオ、ビデオ、画面共有の開始ポートと終了ポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="70110-142">To specify port ranges, next to **Select a port range for each type of real-time media traffic**, select  **Specify port ranges**, and then enter the starting and ending ports for audio, video, and screen sharing.</span></span> <span data-ttu-id="70110-143">QoS を実装するには、このオプションを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70110-143">Selecting this option is required to implement QoS.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="70110-144">[**利用可能なポートを自動的に使用**する] を選択すると、1024と65535の間で利用可能なポートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="70110-144">If you select **Automatically use any available ports**, available ports between 1024 and 65535 are used.</span></span> <span data-ttu-id="70110-145">このオプションは、QoS を実装していない場合にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="70110-145">Use this option only when not implementing QoS.</span></span>
    >
    > <span data-ttu-id="70110-146">狭い範囲のポート範囲を選択すると、通話の中断や音質の低下が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="70110-146">Selecting a port range that is too narrow will lead to dropped calls and poor call quality.</span></span> <span data-ttu-id="70110-147">以下の推奨事項は最小限にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="70110-147">The recommendations below should be a bare minimum.</span></span>

 <span data-ttu-id="70110-148">環境で使用するポートの範囲がわからない場合は、次の設定を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="70110-148">If you are unsure what port ranges to use in your environment, the following settings are a good starting point.</span></span> <span data-ttu-id="70110-149">詳細については、「 [Microsoft Teams でサービスの品質 (QoS) を実装する」](QoS-in-Teams.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70110-149">To learn more, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span> <span data-ttu-id="70110-150">必要な DSCP マーキングと、両方の Teams と ExpressRoute で使用される、対応するメディアポート範囲を示します。</span><span class="sxs-lookup"><span data-stu-id="70110-150">These are the required DSCP markings and the suggested corresponding media port ranges used by both Teams and ExpressRoute.</span></span>

<span data-ttu-id="70110-151">_ポート範囲と DSCP マーキング_</span><span class="sxs-lookup"><span data-stu-id="70110-151">_Port ranges and DSCP markings_</span></span>

<span data-ttu-id="70110-152">メディアトラフィックの種類</span><span class="sxs-lookup"><span data-stu-id="70110-152">Media traffic type</span></span>| <span data-ttu-id="70110-153">クライアントのソースポートの範囲\*</span><span class="sxs-lookup"><span data-stu-id="70110-153">Client source port range \*</span></span> |<span data-ttu-id="70110-154">プロトコル</span><span class="sxs-lookup"><span data-stu-id="70110-154">Protocol</span></span>|<span data-ttu-id="70110-155">DSCP 値</span><span class="sxs-lookup"><span data-stu-id="70110-155">DSCP value</span></span>|<span data-ttu-id="70110-156">DSCP クラス</span><span class="sxs-lookup"><span data-stu-id="70110-156">DSCP class</span></span>|
|:---             |:---                         |:---    |:---      |:---      |
|<span data-ttu-id="70110-157">オーディオ</span><span class="sxs-lookup"><span data-stu-id="70110-157">Audio</span></span>            | <span data-ttu-id="70110-158">50000–50019</span><span class="sxs-lookup"><span data-stu-id="70110-158">50,000–50,019</span></span>               |<span data-ttu-id="70110-159">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="70110-159">TCP/UDP</span></span> |<span data-ttu-id="70110-160">46</span><span class="sxs-lookup"><span data-stu-id="70110-160">46</span></span>        |<span data-ttu-id="70110-161">完全優先転送 (EF)</span><span class="sxs-lookup"><span data-stu-id="70110-161">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="70110-162">ビデオ</span><span class="sxs-lookup"><span data-stu-id="70110-162">Video</span></span>            | <span data-ttu-id="70110-163">50020–50039</span><span class="sxs-lookup"><span data-stu-id="70110-163">50,020–50,039</span></span>               |<span data-ttu-id="70110-164">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="70110-164">TCP/UDP</span></span> |<span data-ttu-id="70110-165">34</span><span class="sxs-lookup"><span data-stu-id="70110-165">34</span></span>        |<span data-ttu-id="70110-166">相対的優先転送 (AF41)</span><span class="sxs-lookup"><span data-stu-id="70110-166">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="70110-167">アプリケーション/画面共有</span><span class="sxs-lookup"><span data-stu-id="70110-167">Application/Screen Sharing</span></span>| <span data-ttu-id="70110-168">50040–50059</span><span class="sxs-lookup"><span data-stu-id="70110-168">50,040–50,059</span></span>      |<span data-ttu-id="70110-169">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="70110-169">TCP/UDP</span></span> |<span data-ttu-id="70110-170">才</span><span class="sxs-lookup"><span data-stu-id="70110-170">18</span></span>        |<span data-ttu-id="70110-171">確実に転送 (AF21)</span><span class="sxs-lookup"><span data-stu-id="70110-171">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="70110-172">\*割り当てたポート範囲は重なり合って、互いに隣り合っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="70110-172">\* The port ranges you assign cannot overlap and must be adjacent to each other.</span></span>

<span data-ttu-id="70110-173">トラフィックの種類ごとにポート範囲を設定することは、リアルタイムメディアを処理する手順の1つにすぎません。詳細については、「 [Teams のサービスの品質 (QoS)](qos-in-teams.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70110-173">Setting port ranges for different traffic types is only one step in handling real time media; see [Quality of Service (QoS) in Teams](qos-in-teams.md) for much more detail.</span></span> <span data-ttu-id="70110-174">Microsoft Teams 管理センターで設定を有効にするか、または変更する場合は、すべてのユーザーデバイスと内部ネットワークデバイス[に一致する設定を適用](QoS-in-Teams-clients.md)して、チーム内の QoS の変更を完全に実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70110-174">If you enable or change settings in the Microsoft Teams admin center, you will need to [apply matching settings to all user devices](QoS-in-Teams-clients.md) and internal network devices to fully implement the changes to QoS in Teams.</span></span>

<span data-ttu-id="70110-175">しばらくの間 QoS が使用された後は、これら3つのワークロードのそれぞれについて、必要に応じて使用に関する情報を入手できます。また、特定のニーズに応じてどのような変更を行うかを選ぶこともできます。</span><span class="sxs-lookup"><span data-stu-id="70110-175">After QoS has been in use for a while, you'll have usage information on the demand for each of these three workloads, and you can choose what changes to make based on your specific needs.</span></span> <span data-ttu-id="70110-176">[通話品質ダッシュボード](turning-on-and-using-call-quality-dashboard.md)は、そのために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="70110-176">[Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md) will be helpful with that.</span></span>
