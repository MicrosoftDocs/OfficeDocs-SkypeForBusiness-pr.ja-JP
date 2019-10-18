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
description: 組織でスケジュールされているユーザーのチーム会議の設定を管理する方法について説明します。
ms.openlocfilehash: 36325fe82c8864850da8e92de385752422e02f72
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37564935"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a><span data-ttu-id="1c3c4-103">Microsoft Teams で会議の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="1c3c4-103">Manage meeting settings in Microsoft Teams</span></span>

<span data-ttu-id="1c3c4-104">管理者として、Teams 会議の設定を使用して、匿名ユーザーが Teams 会議に参加できるかどうかを制御したり、会議出席依頼をカスタマイズしたり、サービスの品質 (QoS) を有効にしたりする場合は、リアルタイムトラフィック用のポート範囲を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-104">As an admin, you use Teams meetings settings to control whether anonymous users can join Teams meetings, customize meeting invitations, and if you want to enable Quality of Service (QoS), set port ranges for real-time traffic.</span></span> <span data-ttu-id="1c3c4-105">これらの設定は、ユーザーが組織でスケジュールしたすべてのチーム会議に適用されます。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-105">These settings apply to all Teams meetings that users schedule in your organization.</span></span> <span data-ttu-id="1c3c4-106">これらの設定は、Microsoft Teams 管理センターの**会議** > の**設定**から管理します。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-106">You manage these settings from **Meetings** > **Meeting settings** in the Microsoft Teams admin center.</span></span>

## <a name="allow-anonymous-users-to-join-meetings"></a><span data-ttu-id="1c3c4-107">匿名ユーザーによる会議への参加を許可する</span><span class="sxs-lookup"><span data-stu-id="1c3c4-107">Allow anonymous users to join meetings</span></span>

<span data-ttu-id="1c3c4-108">匿名の参加では、会議出席依頼のリンクをクリックすると、誰でも匿名ユーザーとして会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-108">With anonymous join, anyone can join the meeting as an anonymous user by clicking the link in the meeting invitation.</span></span>

<span data-ttu-id="1c3c4-109">![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン</span><span class="sxs-lookup"><span data-stu-id="1c3c4-109">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="1c3c4-110">左側のナビゲーションで、[**会議** > の**会議の設定**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-110">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
2. <span data-ttu-id="1c3c4-111">[**参加者**] の下で、[**匿名ユーザーが会議に参加できるよう**にする] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-111">Under **Participants**, turn on **Anonymous users can join a meeting**.</span></span>

    <span data-ttu-id="1c3c4-112">![管理センターでの会議の参加者設定のスクリーンショット](media/meeting-settings-participants.png "Microsoft Teams 管理センターでの Teams 会議の参加者設定のスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="1c3c4-112">![Screenshot of participants settings for meetings in the admin center](media/meeting-settings-participants.png "Screen shot of participants settings for Teams meetings in the Microsoft Teams admin center")</span></span>

<span data-ttu-id="1c3c4-113">組織内のユーザーによってスケジュールされている会議に匿名ユーザーが会議に参加しないようにするには、この設定をオフにします。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-113">If you don't want anonymous users to join meetings scheduled by users in your organization, turn off this setting.</span></span>

## <a name="customize-meeting-invitations"></a><span data-ttu-id="1c3c4-114">会議出席依頼をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="1c3c4-114">Customize meeting invitations</span></span>

<span data-ttu-id="1c3c4-115">組織のニーズに合わせて、Teams の会議出席依頼をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-115">You can customize Teams meeting invitations to meet your organization's needs.</span></span> <span data-ttu-id="1c3c4-116">組織のロゴを追加したり、サポート web サイトや法的免責事項へのリンクやテキストのみのフッターなど、有用な情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-116">You can add your organization's logo and include helpful information, such as links to your support website and legal disclaimer, and a text-only footer.</span></span>

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a><span data-ttu-id="1c3c4-117">会議出席依頼のロゴを作成するためのヒント</span><span class="sxs-lookup"><span data-stu-id="1c3c4-117">Tips for creating a logo for meeting invitations</span></span>  

1. <span data-ttu-id="1c3c4-118">高さが188ピクセル未満で、幅が30ピクセル以下の画像を作成します (非常に小さい)。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-118">Create an image that's no more than 188 pixels wide by 30 pixels tall (it's quite small).</span></span>
2. <span data-ttu-id="1c3c4-119">画像を JPG または PNG 形式で保存します。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-119">Save the image in JPG or PNG format.</span></span>
3. <span data-ttu-id="1c3c4-120">ネットワーク共有など、組織内のすべてのユーザーがアクセスできる一元的な場所に画像を保存します。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-120">Store the image in a central location that everyone in your organization can access, such as a network share.</span></span>

    <span data-ttu-id="1c3c4-121">会議出席依頼に追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-121">Now you can add it to your meeting invitations.</span></span> <span data-ttu-id="1c3c4-122">次の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-122">See the next steps.</span></span>

### <a name="customize-your-meeting-invitations"></a><span data-ttu-id="1c3c4-123">会議出席依頼をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="1c3c4-123">Customize your meeting invitations</span></span>

<span data-ttu-id="1c3c4-124">![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン</span><span class="sxs-lookup"><span data-stu-id="1c3c4-124">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="1c3c4-125">左側のナビゲーションで、[**会議** > の**会議の設定**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-125">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
2. <span data-ttu-id="1c3c4-126">[**電子メールの招待状**] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-126">Under **Email invitation**, do the following:</span></span>

    <span data-ttu-id="1c3c4-127">![カスタマイズできる会議出席依頼の設定のスクリーンショット](media/meeting-settings-invitation.png "チーム会議用にカスタマイズできる会議出席依頼の設定のスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="1c3c4-127">![Screenshot of the meeting invitation settings you can customize](media/meeting-settings-invitation.png "Screen shot of the meeting invitation settings that you can customize for Teams meetings")</span></span>

    - <span data-ttu-id="1c3c4-128">**ロゴ URL**ロゴが保存されている URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-128">**Logo URL** Enter the URL where your logo is stored.</span></span>
    - <span data-ttu-id="1c3c4-129">**法的**情報の URL法的な懸念事項についてユーザーに連絡する法的 web サイトが組織にある場合は、URL をここに入力します。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-129">**Legal URL** If your organization has a legal website that you want people to go to for any legal concerns, enter the URL here.</span></span>
    - <span data-ttu-id="1c3c4-130">**ヘルプ URL**問題が発生した場合にユーザーが移動できるサポート web サイトが組織にある場合は、URL をここに入力します。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-130">**Help URL** If your organization has a support website that you want people to go to if they run into issues, enter the URL here.</span></span>
    - <span data-ttu-id="1c3c4-131">**フッター**フッターとして追加するテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-131">**Footer** Enter text that you want to include as a footer.</span></span>
3. <span data-ttu-id="1c3c4-132">変更を反映させるには1時間ほど待ちます。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-132">Wait an hour or so for the changes to propagate.</span></span> <span data-ttu-id="1c3c4-133">次に、Teams 会議をスケジュールして、会議の出席依頼がどのように表示されるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-133">Then schedule a Teams meeting to see what the meeting invitation looks like.</span></span>  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a><span data-ttu-id="1c3c4-134">Teams 会議でのリアルタイムのメディアトラフィックの処理方法を設定する</span><span class="sxs-lookup"><span data-stu-id="1c3c4-134">Set how you want to handle real-time media traffic for Teams meetings</span></span>

<span data-ttu-id="1c3c4-135"><a name="bknetwork"> </a></span><span class="sxs-lookup"><span data-stu-id="1c3c4-135"></span></span>

<span data-ttu-id="1c3c4-136">Qos (Quality of Service [)](qos-in-teams.md)を使ってネットワークトラフィックの優先順位を設定している場合は、qos マーカーを有効にして、メディアトラフィックごとにポート範囲を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-136">If you're using Quality of Service [(QoS)](qos-in-teams.md) to prioritize network traffic, you can enable QoS markers and you can set port ranges for each type of media traffic.</span></span> <span data-ttu-id="1c3c4-137">トラフィックの種類ごとにポート範囲を設定することは、リアルタイムメディアを処理する手順の1つにすぎません。詳細については、「 [Teams のサービスの品質 (QoS)](qos-in-teams.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-137">Setting port ranges for different traffic types is only one step in handling real-time media; see [Quality of Service (QoS) in Teams](qos-in-teams.md) for much more detail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1c3c4-138">Microsoft Teams サービスの Microsoft Teams 管理センターで QoS を有効にしたり設定を変更したりする場合は、[すべてのユーザーデバイス](QoS-in-Teams-clients.md)とすべての内部ネットワークデバイスに一致する設定を適用して、Teams の QoS への変更を完全に実装する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-138">If you enable QoS or change settings in the Microsoft Teams admin center for the Microsoft Teams service, you will also need to [apply matching settings to all user devices](QoS-in-Teams-clients.md) and all internal network devices to fully implement the changes to QoS in Teams.</span></span>

 <span data-ttu-id="1c3c4-139">![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン</span><span class="sxs-lookup"><span data-stu-id="1c3c4-139">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="1c3c4-140">左側のナビゲーションで、[**会議** > の**会議の設定**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-140">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
2. <span data-ttu-id="1c3c4-141">[**ネットワーク**] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-141">Under **Network**, do the following:</span></span>

    <span data-ttu-id="1c3c4-142">![管理センターでの会議のネットワーク設定のスクリーンショット](media/meeting-settings-network.png "Microsoft Teams 管理センターの Teams 会議のネットワーク設定のスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="1c3c4-142">![Screenshot of the network settings for meetings in the admin center](media/meeting-settings-network.png "Screen shot of the network settings for Teams meetings in the Microsoft Teams admin center")</span></span>

    - <span data-ttu-id="1c3c4-143">QoS に DSCP マーキングを使用できるようにするには、**リアルタイムメディアトラフィックの [サービス品質 (QoS) マーカーの挿入**] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-143">To allow DSCP markings to be used for QoS, turn on **Insert Quality of Service (QoS) markers for real-time media traffic**.</span></span> <span data-ttu-id="1c3c4-144">マーカーを使用するかどうかは選択できません。トラフィックの種類ごとにカスタムマーカーを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-144">You only have the option of using markers or not; you can't set custom markers for each traffic type.</span></span> <span data-ttu-id="1c3c4-145">詳細については[、「QoS の実装方法を選択する](QoS-in-Teams.md#select-a-qos-implementation-method)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-145">See [Select a QoS implementation method](QoS-in-Teams.md#select-a-qos-implementation-method) for more on DSCP markers.</span></span>
    > [!NOTE] 
    > <span data-ttu-id="1c3c4-146">**リアルタイムメディアトラフィックの [サービス品質の挿入 (QoS)] マーカー**を有効にすると、UDP ポート 3479 (オーディオ)、3480 (ビデオ)、3481 (共有) を使用したトランスポートリレーとの通信が可能になります。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-146">Turning on **Insert Quality of Service (QoS) markers for real-time media traffic** will also enable communication to the Transport Relay with UDP ports 3479 (Audio), 3480 (Video) and 3481 (Sharing).</span></span>
    - <span data-ttu-id="1c3c4-147">ポート範囲を指定するには、[ポート範囲の指定] の横にある [ポート範囲の**指定** **] を選択**し、オーディオ、ビデオ、画面共有の開始ポートと終了ポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-147">To specify port ranges, next to **Select a port range for each type of real-time media traffic**, select  **Specify port ranges**, and then enter the starting and ending ports for audio, video, and screen sharing.</span></span> <span data-ttu-id="1c3c4-148">QoS を実装するには、このオプションを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-148">Selecting this option is required to implement QoS.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="1c3c4-149">[**利用可能なポートを自動的に使用**する] を選択すると、1024と65535の間で利用可能なポートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-149">If you select **Automatically use any available ports**, available ports between 1024 and 65535 are used.</span></span> <span data-ttu-id="1c3c4-150">このオプションは、QoS を実装していない場合にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-150">Use this option only when not implementing QoS.</span></span>
    >
    > <span data-ttu-id="1c3c4-151">狭い範囲のポート範囲を選択すると、通話の中断や音質の低下が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-151">Selecting a port range that is too narrow will lead to dropped calls and poor call quality.</span></span> <span data-ttu-id="1c3c4-152">以下の推奨事項は最小限にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-152">The recommendations below should be a bare minimum.</span></span>

<span data-ttu-id="1c3c4-153">環境で使用するポートの範囲がわからない場合は、次の設定を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-153">If you are unsure what port ranges to use in your environment, the following settings are a good starting point.</span></span> <span data-ttu-id="1c3c4-154">詳細については、「 [Microsoft Teams でサービスの品質 (QoS) を実装する」](QoS-in-Teams.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-154">To learn more, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span> <span data-ttu-id="1c3c4-155">必要な DSCP マーキングと、両方の Teams と ExpressRoute で使用される、対応するメディアポート範囲を示します。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-155">These are the required DSCP markings and the suggested corresponding media port ranges used by both Teams and ExpressRoute.</span></span>

<span data-ttu-id="1c3c4-156">_ポート範囲と DSCP マーキング_</span><span class="sxs-lookup"><span data-stu-id="1c3c4-156">_Port ranges and DSCP markings_</span></span>

<span data-ttu-id="1c3c4-157">メディアトラフィックの種類</span><span class="sxs-lookup"><span data-stu-id="1c3c4-157">Media traffic type</span></span>| <span data-ttu-id="1c3c4-158">クライアントのソースポートの範囲\*</span><span class="sxs-lookup"><span data-stu-id="1c3c4-158">Client source port range \*</span></span> |<span data-ttu-id="1c3c4-159">プロトコル</span><span class="sxs-lookup"><span data-stu-id="1c3c4-159">Protocol</span></span>|<span data-ttu-id="1c3c4-160">DSCP 値</span><span class="sxs-lookup"><span data-stu-id="1c3c4-160">DSCP value</span></span>|<span data-ttu-id="1c3c4-161">DSCP クラス</span><span class="sxs-lookup"><span data-stu-id="1c3c4-161">DSCP class</span></span>|
|:---             |:---                         |:---    |:---      |:---      |
|<span data-ttu-id="1c3c4-162">オーディオ</span><span class="sxs-lookup"><span data-stu-id="1c3c4-162">Audio</span></span>            | <span data-ttu-id="1c3c4-163">50000–50019</span><span class="sxs-lookup"><span data-stu-id="1c3c4-163">50,000–50,019</span></span>               |<span data-ttu-id="1c3c4-164">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="1c3c4-164">TCP/UDP</span></span> |<span data-ttu-id="1c3c4-165">46</span><span class="sxs-lookup"><span data-stu-id="1c3c4-165">46</span></span>        |<span data-ttu-id="1c3c4-166">完全優先転送 (EF)</span><span class="sxs-lookup"><span data-stu-id="1c3c4-166">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="1c3c4-167">ビデオ</span><span class="sxs-lookup"><span data-stu-id="1c3c4-167">Video</span></span>            | <span data-ttu-id="1c3c4-168">50020–50039</span><span class="sxs-lookup"><span data-stu-id="1c3c4-168">50,020–50,039</span></span>               |<span data-ttu-id="1c3c4-169">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="1c3c4-169">TCP/UDP</span></span> |<span data-ttu-id="1c3c4-170">34</span><span class="sxs-lookup"><span data-stu-id="1c3c4-170">34</span></span>        |<span data-ttu-id="1c3c4-171">相対的優先転送 (AF41)</span><span class="sxs-lookup"><span data-stu-id="1c3c4-171">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="1c3c4-172">アプリケーション/画面共有</span><span class="sxs-lookup"><span data-stu-id="1c3c4-172">Application/Screen Sharing</span></span>| <span data-ttu-id="1c3c4-173">50040–50059</span><span class="sxs-lookup"><span data-stu-id="1c3c4-173">50,040–50,059</span></span>      |<span data-ttu-id="1c3c4-174">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="1c3c4-174">TCP/UDP</span></span> |<span data-ttu-id="1c3c4-175">才</span><span class="sxs-lookup"><span data-stu-id="1c3c4-175">18</span></span>        |<span data-ttu-id="1c3c4-176">確実に転送 (AF21)</span><span class="sxs-lookup"><span data-stu-id="1c3c4-176">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="1c3c4-177">\*割り当てるポートの範囲は重なり合って、互いに隣り合っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-177">\* The port ranges you assign cannot overlap and must be next to each other.</span></span>

<span data-ttu-id="1c3c4-178">しばらくの間 QoS が使用された後は、これら3つのワークロードのそれぞれについて、必要に応じて使用に関する情報を入手できます。また、特定のニーズに応じてどのような変更を行うかを選ぶこともできます。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-178">After QoS has been in use for a while, you'll have usage information on the demand for each of these three workloads, and you can choose what changes to make based on your specific needs.</span></span> <span data-ttu-id="1c3c4-179">[通話品質ダッシュボード](turning-on-and-using-call-quality-dashboard.md)は、そのために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1c3c4-179">[Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md) will be helpful with that.</span></span>
