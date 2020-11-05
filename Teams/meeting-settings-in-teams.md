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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.invitationurls
- ms.teamsadmincenter.meetingsettings.network.ports
- ms.teamsadmincenter.meetingsettings.overview
ms.collection:
- M365-collaboration
description: 組織のユーザーがスケジュールする Teams 会議の設定を管理する方法を説明します。
ms.openlocfilehash: b231fb1ae564466985195325fb748af5730623a6
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908486"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a><span data-ttu-id="572ef-103">Microsoft Teams で会議の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="572ef-103">Manage meeting settings in Microsoft Teams</span></span>

<span data-ttu-id="572ef-104">管理者は Teams 会議の設定を使用することにより、Teams 会議への匿名ユーザーの参加可否、会議への招待状のカスタマイズ、およびサービスの品質 (QoS) をオンにするかどうかの制御を行え、リアルタイム トラフィックのポート範囲を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="572ef-104">As an admin, you use Teams meetings settings to control whether anonymous users can join Teams meetings, customize meeting invitations, and if you want to enable Quality of Service (QoS), set port ranges for real-time traffic.</span></span> <span data-ttu-id="572ef-105">これらの設定は、組織のユーザーがスケジュールするすべての Teams 会議に適用されます。</span><span class="sxs-lookup"><span data-stu-id="572ef-105">These settings apply to all Teams meetings that users schedule in your organization.</span></span> <span data-ttu-id="572ef-106">これらの設定は、Microsoft Teams 管理センターの [ **会議** ] > [ **会議設定** ] から管理します。</span><span class="sxs-lookup"><span data-stu-id="572ef-106">You manage these settings from **Meetings** > **Meeting settings** in the Microsoft Teams admin center.</span></span>

## <a name="allow-anonymous-users-to-join-meetings"></a><span data-ttu-id="572ef-107">匿名ユーザーによる会議への参加を許可する</span><span class="sxs-lookup"><span data-stu-id="572ef-107">Allow anonymous users to join meetings</span></span>

<span data-ttu-id="572ef-108">匿名参加を許可した場合、会議への招待状に含まれるリンクをクリックすると、誰でも匿名ユーザーとして会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="572ef-108">With anonymous join, anyone can join the meeting as an anonymous user by clicking the link in the meeting invitation.</span></span> <span data-ttu-id="572ef-109">詳細については、「[Teams のアカウントなしに会議に参加する](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="572ef-109">To learn more, see [Join a meeting without a Teams account](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508).</span></span>

<span data-ttu-id="572ef-110">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="572ef-110">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="572ef-111">これらの変更を行うには、Teams サービス管理者であることが必要です。</span><span class="sxs-lookup"><span data-stu-id="572ef-111">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="572ef-112">「[Teams 管理者ロールを使用してチームを管理する](https://docs.microsoft.com/microsoftteams/using-admin-roles)」をご覧いただき、管理者ロールとアクセス許可を取得する方法について読んでください。</span><span class="sxs-lookup"><span data-stu-id="572ef-112">See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="572ef-113">管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="572ef-113">Go to the admin center.</span></span>

2. <span data-ttu-id="572ef-114">左側のナビゲーションで、[ **会議** ] > [ **会議設定** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="572ef-114">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>

3. <span data-ttu-id="572ef-115">[ **参加者** ] の下で、[ **匿名ユーザーが会議に参加できます** ] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="572ef-115">Under **Participants** , turn on **Anonymous users can join a meeting**.</span></span>

    <span data-ttu-id="572ef-116">![管理センターでの会議の参加者設定のスクリーンショット](media/meeting-settings-participants.png "Microsoft Teams 管理センターでの Teams 会議の参加者設定のスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="572ef-116">![Screenshot of participants settings for meetings in the admin center](media/meeting-settings-participants.png "Screenshot of participants settings for Teams meetings in the Microsoft Teams admin center")</span></span>

> [!CAUTION]
> <span data-ttu-id="572ef-117">組織のユーザーがスケジュールを行った会議に匿名ユーザーを参加させないようにするには、この設定をオフにします。</span><span class="sxs-lookup"><span data-stu-id="572ef-117">If you don't want anonymous users to join meetings scheduled by users in your organization, turn off this setting.</span></span>

## <a name="customize-meeting-invitations"></a><span data-ttu-id="572ef-118">会議への招待状をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="572ef-118">Customize meeting invitations</span></span>

<span data-ttu-id="572ef-119">組織のニーズに合わせて Teams 会議への招待状をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="572ef-119">You can customize Teams meeting invitations to meet your organization's needs.</span></span> <span data-ttu-id="572ef-120">組織のロゴを加えたり、役立つ情報 (組織のサポート Web サイトへのリンク、法的免責事項、テキストのみのフッターなど) を含めたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="572ef-120">You can add your organization's logo and include helpful information, such as links to your support website and legal disclaimer, and a text-only footer.</span></span>

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a><span data-ttu-id="572ef-121">会議の招待状用ロゴの作成ヒント</span><span class="sxs-lookup"><span data-stu-id="572ef-121">Tips for creating a logo for meeting invitations</span></span>  

1. <span data-ttu-id="572ef-122">幅 188 ピクセル、高さ 30 ピクセル以内の、ごく小さな画像を作成します。</span><span class="sxs-lookup"><span data-stu-id="572ef-122">Create an image that's no more than 188 pixels wide by 30 pixels tall (it's quite small).</span></span>
2. <span data-ttu-id="572ef-123">画像を JPG または PNG 形式で保存します。</span><span class="sxs-lookup"><span data-stu-id="572ef-123">Save the image in JPG or PNG format.</span></span>
3. <span data-ttu-id="572ef-124">パブリック Web サイトなど、招待状を受け取るすべてのユーザーがアクセス可能な場所に画像を保存します。</span><span class="sxs-lookup"><span data-stu-id="572ef-124">Store the image in a location that everyone receiving the invitation can access, such as a public website.</span></span>

    <span data-ttu-id="572ef-125">会議出席依頼に追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="572ef-125">Now you can add it to your meeting invitations.</span></span> <span data-ttu-id="572ef-126">方法については、次の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="572ef-126">See the next steps.</span></span>

### <a name="customize-your-meeting-invitations"></a><span data-ttu-id="572ef-127">会議の招待状をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="572ef-127">Customize your meeting invitations</span></span>

<span data-ttu-id="572ef-128">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="572ef-128">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="572ef-129">管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="572ef-129">Go to the admin center.</span></span>
2. <span data-ttu-id="572ef-130">左側のナビゲーションで、[ **会議** ] > [ **会議設定** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="572ef-130">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
3. <span data-ttu-id="572ef-131">[ **招待メール** ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="572ef-131">Under **Email invitation** , do the following:</span></span>

    <span data-ttu-id="572ef-132">![カスタマイズ可能な会議の招待状設定のスクリーンショット](media/meeting-settings-invitation.png "Teams 会議用のカスタマイズ可能な会議の招待状設定のスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="572ef-132">![Screenshot of the meeting invitation settings you can customize](media/meeting-settings-invitation.png "Screenshot of the meeting invitation settings that you can customize for Teams meetings")</span></span>

    - <span data-ttu-id="572ef-133">[ **ロゴ URL** ] ロゴの保存場所の URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="572ef-133">**Logo URL** Enter the URL where your logo is stored.</span></span>
    - <span data-ttu-id="572ef-134">[ **法的事項の URL** ] 法的な質問があるユーザーを誘導することができる、法的情報が記載されている Web サイトが組織にある場合は、こちらに URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="572ef-134">**Legal URL** If your organization has a legal website that you want people to go to for any legal concerns, enter the URL here.</span></span>
    - <span data-ttu-id="572ef-135">[ **ヘルプの URL** ] ユーザーに問題が発生した場合にユーザーを誘導することができる、サポート Web サイトが組織にある場合は、こちらに URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="572ef-135">**Help URL** If your organization has a support website that you want people to go to if they run into issues, enter the URL here.</span></span>
    - <span data-ttu-id="572ef-136">[ **フッター** ] フッターとして含めるテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="572ef-136">**Footer** Enter text that you want to include as a footer.</span></span>
4. <span data-ttu-id="572ef-137">**[Preview invite]** (出席依頼のプレビュー) をクリックして、会議出席依頼のプレビューを表示します。</span><span class="sxs-lookup"><span data-stu-id="572ef-137">Click **Preview invite** to see a preview of your meeting invitation.</span></span>
5. <span data-ttu-id="572ef-138">作業を終えたら、 **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="572ef-138">When you're done, click **Save**.</span></span>
6. <span data-ttu-id="572ef-139">変更が反映されるまで、約 1 時間待ちます。</span><span class="sxs-lookup"><span data-stu-id="572ef-139">Wait an hour or so for the changes to propagate.</span></span> <span data-ttu-id="572ef-140">その後、Team 会議をスケジュールし、会議の招待状の表示のされ方を確認します。</span><span class="sxs-lookup"><span data-stu-id="572ef-140">Then schedule a Teams meeting to see what the meeting invitation looks like.</span></span>  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a><span data-ttu-id="572ef-141">Teams 会議でのリアルタイム メディア トラフィックの処理方法を設定する</span><span class="sxs-lookup"><span data-stu-id="572ef-141">Set how you want to handle real-time media traffic for Teams meetings</span></span>

<span data-ttu-id="572ef-142"><a name="bknetwork"> </a></span><span class="sxs-lookup"><span data-stu-id="572ef-142"><a name="bknetwork"> </a></span></span>

<span data-ttu-id="572ef-143">QoS (Quality of Service) を使ってネットワークトラフィックの優先順位を設定している場合は、QoS マーカーを有効にし、各種類のメディアトラフィックに対してポート範囲を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="572ef-143">If you're using Quality of Service (QoS)to prioritize network traffic, you can enable QoS markers and set port ranges for each type of media traffic.</span></span> <span data-ttu-id="572ef-144">トラフィックの種類ごとのポート範囲の設定は、リアルタイム メディアの処理に関する手順のうちの 1 つに過ぎません。詳細については、「[Teams でのサービスの品質 (QoS)](qos-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="572ef-144">Setting port ranges for different traffic types is only one step in handling real-time media; see [Quality of Service (QoS) in Teams](qos-in-teams.md) for much more detail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="572ef-145">Teams サービスの Microsoft Teams 管理センターで QoS を有効にしたり設定を変更したりする場合は、 [すべてのユーザーデバイス](QoS-in-Teams-clients.md) とすべての内部ネットワークデバイスに一致する設定を適用して、Teams の QoS への変更を完全に実装する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="572ef-145">If you enable QoS or change settings in the Microsoft Teams admin center for the Teams service, you'll also need to [apply matching settings to all user devices](QoS-in-Teams-clients.md) and all internal network devices to fully implement the changes to QoS in Teams.</span></span>

 <span data-ttu-id="572ef-146">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="572ef-146">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>
1. <span data-ttu-id="572ef-147">管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="572ef-147">Go to the admin center.</span></span>
2. <span data-ttu-id="572ef-148">左側のナビゲーションで、[ **会議** ] > [ **会議設定** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="572ef-148">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
3. <span data-ttu-id="572ef-149">[ **ネットワーク** ] で、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="572ef-149">Under **Network** , do the following:</span></span>

    <span data-ttu-id="572ef-150">![管理センターでの会議のネットワーク設定のスクリーンショット](media/meeting-settings-network.png "Microsoft Teams 管理センターでの Teams 会議のネットワーク設定のスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="572ef-150">![Screenshot of the network settings for meetings in the admin center](media/meeting-settings-network.png "Screenshot of the network settings for Teams meetings in the Microsoft Teams admin center")</span></span>

    - <span data-ttu-id="572ef-151">DSCP マーキングを QoS で使用できるようにするには、[ **リアルタイム メディア トラフィックのサービスの品質 (QoS) マーカーを挿入する** ] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="572ef-151">To allow DSCP markings to be used for QoS, turn on **Insert Quality of Service (QoS) markers for real-time media traffic**.</span></span> <span data-ttu-id="572ef-152">選択できるのは、マーカーを使用するか使用しないかのどちらかです。トラフィックの種類ごとにカスタム マーカーを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="572ef-152">You only have the option of using markers or not; you can't set custom markers for each traffic type.</span></span> <span data-ttu-id="572ef-153">DSCP マーカーの詳細については、「[QoS の実装方法を選択する](QoS-in-Teams.md#select-a-qos-implementation-method)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="572ef-153">See [Select a QoS implementation method](QoS-in-Teams.md#select-a-qos-implementation-method) for more on DSCP markers.</span></span>
        > [!NOTE]
        > <span data-ttu-id="572ef-154">DSCP タグ処理は通常、ソースポート経由で行われます。 UDP トラフィックは、既定で3478の宛先ポートを使ってトランスポートリレーにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="572ef-154">DSCP tagging is typically done via Source Ports and UDP traffic will route to Transport Relay with destination port of 3478 by default.</span></span> <span data-ttu-id="572ef-155">会社で宛先ポートのタグ付けが必要な場合は、サポートに連絡して、UDP ポート 3479 (オーディオ)、3480 (ビデオ)、3481 (共有) を使用したトランスポートリレーとの通信を有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="572ef-155">If your company requires tagging on destination ports, please contact support to enable communication to the Transport Relay with UDP ports 3479 (Audio), 3480 (Video), and 3481 (Sharing).</span></span>
    - <span data-ttu-id="572ef-156">ポート範囲を指定するには、[ **リアルタイム メディア トラフィックの種類ごとのポート範囲を選択する** ] の横にある [ **ポート範囲を指定** ] を選択し、オーディオ、ビデオ、画面共有用の開始および終了ポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="572ef-156">To specify port ranges, next to **Select a port range for each type of real-time media traffic** , select  **Specify port ranges** , and then enter the starting and ending ports for audio, video, and screen sharing.</span></span> <span data-ttu-id="572ef-157">QoS を実装するには、このオプションを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="572ef-157">Selecting this option is required to implement QoS.</span></span> 
        > [!Note]
        > <span data-ttu-id="572ef-158">**リアルタイムメディアトラフィックの qos (Quality Of Service) マーカー** がオンになっている場合は、ポート設定を管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="572ef-158">If **Quality of Service (QoS) markers for real-time media traffic** is on, then you have to manage your port settings.</span></span> <span data-ttu-id="572ef-159">自動的には管理されません。</span><span class="sxs-lookup"><span data-stu-id="572ef-159">They aren't managed automatically.</span></span>
        
        > [!IMPORTANT]
        > <span data-ttu-id="572ef-160">[ **任意の利用可能なポートを自動的に使用する** ] を選択すると、1024 と 65535 の間の利用可能なポートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="572ef-160">If you select **Automatically use any available ports** , available ports between 1024 and 65535 are used.</span></span> <span data-ttu-id="572ef-161">このオプションは、QoS を実装しない場合にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="572ef-161">Use this option only when not implementing QoS.</span></span>
        >
        > <span data-ttu-id="572ef-162">範囲が狭すぎるポート範囲を選択すると、通話の中断や通話の品質低下が発生します。</span><span class="sxs-lookup"><span data-stu-id="572ef-162">Selecting a port range that is too narrow will lead to dropped calls and poor call quality.</span></span> <span data-ttu-id="572ef-163">以下の推奨事項は、最低限のものです。</span><span class="sxs-lookup"><span data-stu-id="572ef-163">The recommendations below should be a bare minimum.</span></span>

<span data-ttu-id="572ef-164">お客様の環境で使用すべきポート範囲がわからない場合は、以下の設定から始めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="572ef-164">If you're unsure what port ranges to use in your environment, the following settings are a good starting point.</span></span> <span data-ttu-id="572ef-165">詳細については、「[Microsoft Teams でサービスの品質 (QoS) を実装する](QoS-in-Teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="572ef-165">To learn more, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span> <span data-ttu-id="572ef-166">必要な DSCP マーキングと、Teams と ExpressRoute の両方で使用される、対応する推奨メディア ポートの範囲を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="572ef-166">These are the required DSCP markings and the suggested corresponding media port ranges used by both Teams and ExpressRoute.</span></span>

### <a name="port-ranges-and-dscp-markings"></a><span data-ttu-id="572ef-167">ポート範囲と DSCP マーカー</span><span class="sxs-lookup"><span data-stu-id="572ef-167">Port ranges and DSCP markings</span></span>

<span data-ttu-id="572ef-168">メディア トラフィックの種類</span><span class="sxs-lookup"><span data-stu-id="572ef-168">Media traffic type</span></span>| <span data-ttu-id="572ef-169">クライアントのソース ポートの範囲\*</span><span class="sxs-lookup"><span data-stu-id="572ef-169">Client source port range \*</span></span> |<span data-ttu-id="572ef-170">プロトコル</span><span class="sxs-lookup"><span data-stu-id="572ef-170">Protocol</span></span>|<span data-ttu-id="572ef-171">DSCP 値</span><span class="sxs-lookup"><span data-stu-id="572ef-171">DSCP value</span></span>|<span data-ttu-id="572ef-172">DSCP クラス</span><span class="sxs-lookup"><span data-stu-id="572ef-172">DSCP class</span></span>|
|:---             |:---                         |:---    |:---      |:---      |
|<span data-ttu-id="572ef-173">オーディオ</span><span class="sxs-lookup"><span data-stu-id="572ef-173">Audio</span></span>            | <span data-ttu-id="572ef-174">50,000–50,019</span><span class="sxs-lookup"><span data-stu-id="572ef-174">50,000–50,019</span></span>               |<span data-ttu-id="572ef-175">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="572ef-175">TCP/UDP</span></span> |<span data-ttu-id="572ef-176">46</span><span class="sxs-lookup"><span data-stu-id="572ef-176">46</span></span>        |<span data-ttu-id="572ef-177">完全優先転送 (EF)</span><span class="sxs-lookup"><span data-stu-id="572ef-177">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="572ef-178">ビデオ</span><span class="sxs-lookup"><span data-stu-id="572ef-178">Video</span></span>            | <span data-ttu-id="572ef-179">50,020–50,039</span><span class="sxs-lookup"><span data-stu-id="572ef-179">50,020–50,039</span></span>               |<span data-ttu-id="572ef-180">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="572ef-180">TCP/UDP</span></span> |<span data-ttu-id="572ef-181">34</span><span class="sxs-lookup"><span data-stu-id="572ef-181">34</span></span>        |<span data-ttu-id="572ef-182">相対的優先転送 (AF41)</span><span class="sxs-lookup"><span data-stu-id="572ef-182">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="572ef-183">アプリケーション/画面共有</span><span class="sxs-lookup"><span data-stu-id="572ef-183">Application/Screen Sharing</span></span>| <span data-ttu-id="572ef-184">50,040–50,059</span><span class="sxs-lookup"><span data-stu-id="572ef-184">50,040–50,059</span></span>      |<span data-ttu-id="572ef-185">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="572ef-185">TCP/UDP</span></span> |<span data-ttu-id="572ef-186">才</span><span class="sxs-lookup"><span data-stu-id="572ef-186">18</span></span>        |<span data-ttu-id="572ef-187">相対的優先転送 (AF21)</span><span class="sxs-lookup"><span data-stu-id="572ef-187">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="572ef-188">\* 割り当てたポート範囲は重なり合っていて、互いに隣り合っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="572ef-188">\* The port ranges you assign can't overlap and should be adjacent to each other.</span></span>

<span data-ttu-id="572ef-189">QoS をしばらくの期間使用すると、これらの 3 つのワークロードのそれぞれの需要に関する使用状況情報を入手できます。具体的なニーズに応じて、変更が必要な点を決められます。</span><span class="sxs-lookup"><span data-stu-id="572ef-189">After QoS has been in use for a while, you'll have usage information on the demand for each of these three workloads, and you can choose what changes to make based on your specific needs.</span></span> <span data-ttu-id="572ef-190">この作業を行う上で、[通話品質ダッシュボード](turning-on-and-using-call-quality-dashboard.md)が役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="572ef-190">[Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md) will be helpful with that.</span></span>
