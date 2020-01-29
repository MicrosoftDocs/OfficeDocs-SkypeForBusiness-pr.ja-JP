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
- ms.teamsadmincenter.meetingsettings.invitationurls
- ms.teamsadmincenter.meetingsettings.network.ports
- ms.teamsadmincenter.meetingsettings.overview
ms.collection:
- M365-collaboration
description: 組織のユーザーがスケジュールする Teams 会議の設定を管理する方法を説明します。
ms.openlocfilehash: adb1beaa7aff84d2ef51820332bc7f823b124a22
ms.sourcegitcommit: dc240b123efb03d5ab0545d650a973bf60d04506
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2019
ms.locfileid: "40069458"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a><span data-ttu-id="673c0-103">Microsoft Teams で会議の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="673c0-103">Manage meeting settings in Microsoft Teams</span></span>

<span data-ttu-id="673c0-104">管理者は Teams 会議の設定を使用することにより、Teams 会議への匿名ユーザーの参加可否、会議への招待状のカスタマイズ、およびサービスの品質 (QoS) をオンにするかどうかの制御を行え、リアルタイム トラフィックのポート範囲を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="673c0-104">As an admin, you use Teams meetings settings to control whether anonymous users can join Teams meetings, customize meeting invitations, and if you want to enable Quality of Service (QoS), set port ranges for real-time traffic.</span></span> <span data-ttu-id="673c0-105">これらの設定は、組織のユーザーがスケジュールするすべての Teams 会議に適用されます。</span><span class="sxs-lookup"><span data-stu-id="673c0-105">These settings will be used for all of the Teams meetings that users schedule in your organization.</span></span> <span data-ttu-id="673c0-106">これらの設定は、Microsoft Teams 管理センターの [**会議**] > [**会議設定**] から管理します。</span><span class="sxs-lookup"><span data-stu-id="673c0-106">You manage these settings from **Meetings** > **Meeting settings** in the Microsoft Teams admin center.</span></span>

## <a name="allow-anonymous-users-to-join-meetings"></a><span data-ttu-id="673c0-107">匿名ユーザーによる会議への参加を許可する</span><span class="sxs-lookup"><span data-stu-id="673c0-107">Allow anonymous users to join meetings</span></span>

<span data-ttu-id="673c0-108">匿名参加を許可した場合、会議への招待状に含まれるリンクをクリックすると、誰でも匿名ユーザーとして会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="673c0-108">With anonymous join, anyone can join the meeting as an anonymous user by clicking the link in the meeting invitation.</span></span> <span data-ttu-id="673c0-109">詳細については、「[Teams のアカウントなしに会議に参加する](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="673c0-109">To learn more, see [Join a meeting without a Teams account](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508).</span></span>


<span data-ttu-id="673c0-110">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="673c0-110">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="673c0-111">左側のナビゲーションで、[**会議**] > [**会議設定**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="673c0-111">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="673c0-112">[**参加者**] の下で、[**匿名ユーザーが会議に参加できます**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="673c0-112">Under **Participants**, turn on **Anonymous users can join a meeting**.</span></span>

    <span data-ttu-id="673c0-113">![管理センターでの会議の参加者設定のスクリーンショット](media/meeting-settings-participants.png "Microsoft Teams 管理センターでの Teams 会議の参加者設定のスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="673c0-113">![Screenshot of participants settings for meetings in the admin center](media/meeting-settings-participants.png "Screenshot of participants settings for Teams meetings in the Microsoft Teams admin center")</span></span>

<span data-ttu-id="673c0-114">組織のユーザーがスケジュールを行った会議に匿名ユーザーを参加させないようにするには、この設定をオフにします。</span><span class="sxs-lookup"><span data-stu-id="673c0-114">If you don't want anonymous users to join meetings scheduled by users in your organization, turn off this setting.</span></span>

## <a name="customize-meeting-invitations"></a><span data-ttu-id="673c0-115">会議への招待状をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="673c0-115">Customize meeting invitations</span></span>

<span data-ttu-id="673c0-116">組織のニーズに合わせて Teams 会議への招待状をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="673c0-116">You can customize Teams meeting invitations to meet your organization's needs.</span></span> <span data-ttu-id="673c0-117">組織のロゴを加えたり、役立つ情報 (組織のサポート Web サイトへのリンク、法的免責事項、テキストのみのフッターなど) を含めたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="673c0-117">You can add your organization's logo and include helpful information, such as links to your support website and legal disclaimer, and a text-only footer.</span></span>

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a><span data-ttu-id="673c0-118">会議の招待状用ロゴの作成ヒント</span><span class="sxs-lookup"><span data-stu-id="673c0-118">Tips for creating a logo for meeting invitations</span></span>  

1. <span data-ttu-id="673c0-119">幅 188 ピクセル、高さ 30 ピクセル以内の、ごく小さな画像を作成します。</span><span class="sxs-lookup"><span data-stu-id="673c0-119">Create an image that is no more than 188 pixels wide by 30 pixels tall (it's quite small).</span></span>
2. <span data-ttu-id="673c0-120">画像を JPG または PNG 形式で保存します。</span><span class="sxs-lookup"><span data-stu-id="673c0-120">Save the image in JPG format.</span></span>
3. <span data-ttu-id="673c0-121">パブリック Web サイトなど、招待状を受け取るすべてのユーザーがアクセス可能な場所に画像を保存します。</span><span class="sxs-lookup"><span data-stu-id="673c0-121">Store the image in a location that everyone receiving the invitation can access, such as a public website.</span></span>

    <span data-ttu-id="673c0-122">会議出席依頼に追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="673c0-122">Now you can add it to your meeting invitations.</span></span> <span data-ttu-id="673c0-123">方法については、次の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="673c0-123">See the next section.</span></span>

### <a name="customize-your-meeting-invitations"></a><span data-ttu-id="673c0-124">会議の招待状をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="673c0-124">Customize meeting invitations</span></span>

<span data-ttu-id="673c0-125">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="673c0-125">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="673c0-126">左側のナビゲーションで、[**会議**] > [**会議設定**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="673c0-126">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="673c0-127">[**招待メール**] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="673c0-127">Under **Email invitation**, do the following:</span></span>

    <span data-ttu-id="673c0-128">![カスタマイズ可能な会議の招待状設定のスクリーンショット](media/meeting-settings-invitation.png "Teams 会議用のカスタマイズ可能な会議の招待状設定のスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="673c0-128">![Screenshot of the meeting invitation settings you can customize](media/meeting-settings-invitation.png "Screenshot of the meeting invitation settings that you can customize for Teams meetings")</span></span>

    - <span data-ttu-id="673c0-129">[**ロゴ URL**] ロゴの保存場所の URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="673c0-129">**Logo URL:** Enter the URL where your logo is stored.</span></span>
    - <span data-ttu-id="673c0-130">[**法的情報の URL**] 法的な質問があるユーザーを誘導することができる、法的情報が記載されている Web サイトが組織にある場合は、こちらに URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="673c0-130">**Legal URL:** If your organization has a legal website you want people to go to if they have legal concerns, enter the URL here.</span></span>
    - <span data-ttu-id="673c0-131">[**ヘルプの URL**] ユーザーに問題が発生した場合にユーザーを誘導することができる、サポート Web サイトが組織にある場合は、こちらに URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="673c0-131">**Help URL:** If your organization has a support website you want people to go to if they have problems, enter the URL here.</span></span>
    - <span data-ttu-id="673c0-132">[**フッター**] フッターとして含めるテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="673c0-132">**Footer** Enter text that you want to include as a footer.</span></span>
3. <span data-ttu-id="673c0-133">変更が反映されるまで、約 1 時間待ちます。</span><span class="sxs-lookup"><span data-stu-id="673c0-133">Wait an hour or so for the changes to get populated across all Office 365 services.</span></span> <span data-ttu-id="673c0-134">その後、Team 会議をスケジュールし、会議の招待状の表示のされ方を確認します。</span><span class="sxs-lookup"><span data-stu-id="673c0-134">Then schedule a Teams meeting to see what the meeting invitation looks like.</span></span>  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a><span data-ttu-id="673c0-135">Teams 会議でのリアルタイム メディア トラフィックの処理方法を設定する</span><span class="sxs-lookup"><span data-stu-id="673c0-135">Set how you want to handle real-time media traffic for Teams meetings</span></span>

<span data-ttu-id="673c0-136"><a name="bknetwork"> </a></span><span class="sxs-lookup"><span data-stu-id="673c0-136"></span></span>

<span data-ttu-id="673c0-137">ネットワーク トラフィックの優先順位を付けるためにサービスの品質 [(QoS)](qos-in-teams.md) を使用している場合は、QoS マーカーを有効にしたり、メディア トラフィックの種類ごとにポート範囲を設定したりできます。</span><span class="sxs-lookup"><span data-stu-id="673c0-137">If you're using Quality of Service [(QoS)](qos-in-teams.md) to prioritize network traffic, you can enable QoS markers and you can set port ranges for each type of media traffic.</span></span> <span data-ttu-id="673c0-138">トラフィックの種類ごとのポート範囲の設定は、リアルタイム メディアの処理に関する手順のうちの 1 つに過ぎません。詳細については、「[Teams でのサービスの品質 (QoS)](qos-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="673c0-138">Setting port ranges for different traffic types is only one step in handling real-time media; see [Quality of Service (QoS) in Teams](qos-in-teams.md) for much more detail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="673c0-139">QoS を有効にするか Microsoft Teams サービスに関する設定を Microsoft Teams 管理センターで変更する場合、Teams の QoS への変更を完全に実装するには、[すべてのユーザー デバイスおよびすべてのネットワーク デバイスに対して対応する設定を適用](QoS-in-Teams-clients.md)する必要があいります。</span><span class="sxs-lookup"><span data-stu-id="673c0-139">If you enable QoS or change settings in the Microsoft Teams admin center for the Microsoft Teams service, you will also need to [apply matching settings to all user devices](QoS-in-Teams-clients.md) and all internal network devices to fully implement the changes to QoS in Teams.</span></span>

 <span data-ttu-id="673c0-140">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="673c0-140">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="673c0-141">左側のナビゲーションで、[**会議**] > [**会議設定**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="673c0-141">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="673c0-142">[**ネットワーク**] で、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="673c0-142">Under **Network**, do the following:</span></span>

    <span data-ttu-id="673c0-143">![管理センターでの会議のネットワーク設定のスクリーンショット](media/meeting-settings-network.png "Microsoft Teams 管理センターでの Teams 会議のネットワーク設定のスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="673c0-143">![Screenshot of the settings in the Microsoft Teams admin center.](media/meeting-settings-network.png "Screenshot of the settings in the Microsoft Teams admin center.")</span></span>

    - <span data-ttu-id="673c0-144">DSCP マーキングを QoS で使用できるようにするには、[**リアルタイム メディア トラフィックのサービスの品質 (QoS) マーカーを挿入する**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="673c0-144">To allow DSCP markings to be used for QoS, turn on **Insert Quality of Service (QoS) markers for real-time media traffic**.</span></span> <span data-ttu-id="673c0-145">選択できるのは、マーカーを使用するか使用しないかのどちらかです。トラフィックの種類ごとにカスタム マーカーを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="673c0-145">You only have the option of using markers or not; you can't set custom markers for each traffic type.</span></span> <span data-ttu-id="673c0-146">DSCP マーカーの詳細については、「[QoS の実装方法を選択する](QoS-in-Teams.md#select-a-qos-implementation-method)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="673c0-146">See [Select a QoS implementation method](QoS-in-Teams.md#select-a-qos-implementation-method) for more on DSCP markers.</span></span>
    > [!NOTE] 
    > <span data-ttu-id="673c0-147">[**リアルタイム メディア トラフィックのサービスの品質 (QoS) マーカーを挿入する**] をオンにすると、UDP ポート 3479 (オーディオ), 3480 (ビデオ)、および 3481 (共有) を使用するトランスポート リレーへの通信もオンになります。</span><span class="sxs-lookup"><span data-stu-id="673c0-147">Turning on **Insert Quality of Service (QoS) markers for real-time media traffic** will also enable communication to the Transport Relay with UDP ports 3479 (Audio), 3480 (Video) and 3481 (Sharing).</span></span>
    - <span data-ttu-id="673c0-148">ポート範囲を指定するには、[**リアルタイム メディア トラフィックの種類ごとのポート範囲を選択する**] の横にある [**ポート範囲を指定**] を選択し、オーディオ、ビデオ、画面共有用の開始および終了ポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="673c0-148">To specify port ranges, next to **Select a port range for each type of real-time media traffic**, select  **Specify port ranges**, and then enter the starting and ending ports for audio, video, and screen sharing.</span></span> <span data-ttu-id="673c0-149">QoS を実装するには、このオプションを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="673c0-149">Selecting this option is required to implement QoS.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="673c0-150">[**任意の利用可能なポートを自動的に使用する**] を選択すると、1024 と 65535 の間の利用可能なポートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="673c0-150">If you select **Automatically use any available ports**, available ports between 1024 and 65535 are used.</span></span> <span data-ttu-id="673c0-151">このオプションは、QoS を実装しない場合にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="673c0-151">Use this option only when not implementing QoS.</span></span>
    >
    > <span data-ttu-id="673c0-152">範囲が狭すぎるポート範囲を選択すると、通話の中断や通話の品質低下が発生します。</span><span class="sxs-lookup"><span data-stu-id="673c0-152">Selecting a port range that is too narrow will lead to dropped calls and poor call quality.</span></span> <span data-ttu-id="673c0-153">以下の推奨事項は、最低限のものです。</span><span class="sxs-lookup"><span data-stu-id="673c0-153">The recommendations below should be a bare minimum.</span></span>

<span data-ttu-id="673c0-154">お客様の環境で使用すべきポート範囲が分からない場合は、以下の設定から始めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="673c0-154">If you are unsure what port ranges to use in your environment, the following settings are a good starting point.</span></span> <span data-ttu-id="673c0-155">詳細については、「[Microsoft Teams でサービスの品質 (QoS) を実装する](QoS-in-Teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="673c0-155">To learn more, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span> <span data-ttu-id="673c0-156">必要な DSCP マーキングと、Teams と ExpressRoute の両方で使用される、対応する推奨メディア ポートの範囲を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="673c0-156">These are the required DSCP markings and the suggested corresponding media port ranges used by both Teams and ExpressRoute.</span></span>

<span data-ttu-id="673c0-157">_ポート範囲と DSCP マーカー_</span><span class="sxs-lookup"><span data-stu-id="673c0-157">_Port ranges and DSCP markings_</span></span>

<span data-ttu-id="673c0-158">メディア トラフィックの種類</span><span class="sxs-lookup"><span data-stu-id="673c0-158">Media traffic type</span></span>| <span data-ttu-id="673c0-159">クライアントのソース ポートの範囲\*</span><span class="sxs-lookup"><span data-stu-id="673c0-159">Client source port\*</span></span> |<span data-ttu-id="673c0-160">プロトコル</span><span class="sxs-lookup"><span data-stu-id="673c0-160">Protocol</span></span>|<span data-ttu-id="673c0-161">DSCP 値</span><span class="sxs-lookup"><span data-stu-id="673c0-161">DSCP value</span></span>|<span data-ttu-id="673c0-162">DSCP クラス</span><span class="sxs-lookup"><span data-stu-id="673c0-162">DSCP class</span></span>|
|:---             |:---                         |:---    |:---      |:---      |
|<span data-ttu-id="673c0-163">オーディオ</span><span class="sxs-lookup"><span data-stu-id="673c0-163">Audio</span></span>            | <span data-ttu-id="673c0-164">50,000–50,019</span><span class="sxs-lookup"><span data-stu-id="673c0-164">50000-50019</span></span>               |<span data-ttu-id="673c0-165">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="673c0-165">TCP/UDP</span></span> |<span data-ttu-id="673c0-166">46</span><span class="sxs-lookup"><span data-stu-id="673c0-166">46</span></span>        |<span data-ttu-id="673c0-167">完全優先転送 (EF)</span><span class="sxs-lookup"><span data-stu-id="673c0-167">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="673c0-168">ビデオ</span><span class="sxs-lookup"><span data-stu-id="673c0-168">Video</span></span>            | <span data-ttu-id="673c0-169">50,020–50,039</span><span class="sxs-lookup"><span data-stu-id="673c0-169">50,020–50,039</span></span>               |<span data-ttu-id="673c0-170">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="673c0-170">TCP/UDP</span></span> |<span data-ttu-id="673c0-171">34</span><span class="sxs-lookup"><span data-stu-id="673c0-171">3-4</span></span>        |<span data-ttu-id="673c0-172">相対的優先転送 (AF41)</span><span class="sxs-lookup"><span data-stu-id="673c0-172">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="673c0-173">アプリケーション/画面共有</span><span class="sxs-lookup"><span data-stu-id="673c0-173">Application/Screen Sharing</span></span>| <span data-ttu-id="673c0-174">50,040–50,059</span><span class="sxs-lookup"><span data-stu-id="673c0-174">50,040–50,059</span></span>      |<span data-ttu-id="673c0-175">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="673c0-175">TCP/UDP</span></span> |<span data-ttu-id="673c0-176">18</span><span class="sxs-lookup"><span data-stu-id="673c0-176">18</span></span>        |<span data-ttu-id="673c0-177">相対的優先転送 (AF21)</span><span class="sxs-lookup"><span data-stu-id="673c0-177">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="673c0-178">\* 割り当てるポート範囲は重複させることはできず、互いに隣り合っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="673c0-178">\* The port ranges you assign cannot overlap and must be next to each other.</span></span>

<span data-ttu-id="673c0-179">QoS をしばらくの期間使用すると、これらの 3 つのワークロードのそれぞれの需要に関する使用状況情報を入手できます。具体的なニーズに応じて、変更が必要な点を決められます。</span><span class="sxs-lookup"><span data-stu-id="673c0-179">After QoS has been in use for a while, you'll have usage information on the demand for each of these three workloads, and you can choose what changes to make based on your specific needs.</span></span> <span data-ttu-id="673c0-180">この作業を行う上で、[通話品質ダッシュボード](turning-on-and-using-call-quality-dashboard.md)が役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="673c0-180">[Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md) will be helpful with that.</span></span>
