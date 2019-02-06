---
title: Microsoft Teams で会議の設定を管理する
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
f1keywords: ms.teamsadmincenter.meetingsettings.overview
MS.collection: Teams_ITAdmin_Help
description: 組織内のユーザーのスケジュールを設定するチームの会議の設定を管理する方法について説明します。
ms.openlocfilehash: e4eba5f585f7621add95101d06194bebead507e2
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754418"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a><span data-ttu-id="bd7fc-103">Microsoft Teams で会議の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="bd7fc-103">Manage meeting settings in Microsoft Teams</span></span>

<span data-ttu-id="bd7fc-104">管理者と匿名ユーザーは、チームのミーティングに参加、ミーティングの招待状をカスタマイズ、およびサービスの品質 (QoS) を有効にする場合は、リアルタイムのトラフィック用のポートを設定するかどうかのチーム ミーティングを制御する設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="bd7fc-104">As an admin, you use Teams meetings settings to control whether anonymous users can join Teams meetings, customize meeting invitations, and if you want to enable Quality of Service (QoS), set ports for real-time traffic.</span></span> <span data-ttu-id="bd7fc-105">これらの設定は、組織内でそのユーザーのスケジュールをチームのすべての会議に適用されます。</span><span class="sxs-lookup"><span data-stu-id="bd7fc-105">These settings apply to all Teams meetings that users schedule in your organization.</span></span> <span data-ttu-id="bd7fc-106">**会議**からこれらの設定を管理する > マイクロソフト チームの管理センターでの**会議を設定**します。</span><span class="sxs-lookup"><span data-stu-id="bd7fc-106">You manage these settings from **Meetings** > **Meeting settings** in the Microsoft Teams admin center.</span></span> 

## <a name="allow-anonymous-users-to-join-meetings"></a><span data-ttu-id="bd7fc-107">匿名ユーザーが会議に参加できるように</span><span class="sxs-lookup"><span data-stu-id="bd7fc-107">Allow anonymous users to join meetings</span></span>

<span data-ttu-id="bd7fc-108">匿名結合は、ミーティング招待状のリンクをクリックすると、匿名ユーザーとして会議に参加誰でもできます。</span><span class="sxs-lookup"><span data-stu-id="bd7fc-108">With anonymous join, anyone can join the meeting as an anonymous user by clicking the link in the meeting invitation.</span></span> 

<span data-ttu-id="bd7fc-109">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**</span><span class="sxs-lookup"><span data-stu-id="bd7fc-109">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>
1. <span data-ttu-id="bd7fc-110">左側のナビゲーションでは、**会議**に移動 > **会議を設定**します。</span><span class="sxs-lookup"><span data-stu-id="bd7fc-110">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span> 
2. <span data-ttu-id="bd7fc-111">**参加者**の下でオンに**匿名ユーザーが会議に参加できます**。</span><span class="sxs-lookup"><span data-stu-id="bd7fc-111">Under **Participants**, turn on **Anonymous users can join a meeting**.</span></span> 

    <span data-ttu-id="bd7fc-112">![会議の設定-participants.png](media/meeting-settings-participants.png "マイクロソフトのチームの管理センターでのチーム会議の参加者の設定のスクリーン ショット")</span><span class="sxs-lookup"><span data-stu-id="bd7fc-112">![meeting-settings-participants.png](media/meeting-settings-participants.png "Screen shot of participants settings for Teams meetings in the Microsoft Teams admin center")</span></span>

<span data-ttu-id="bd7fc-113">匿名ユーザーは、組織内のユーザーがスケジュールしたミーティングに参加しない場合は、この設定をオフにします。</span><span class="sxs-lookup"><span data-stu-id="bd7fc-113">If you don't want anonymous users to join meetings scheduled by users in your organization, turn off this setting.</span></span> 

## <a name="customize-meeting-invitations"></a><span data-ttu-id="bd7fc-114">会議出席依頼をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="bd7fc-114">Customize meeting invitations</span></span>

<span data-ttu-id="bd7fc-115">組織のニーズを満たすためにチームのミーティングの招待状をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="bd7fc-115">You can customize Teams meeting invitations to meet your organization's needs.</span></span> <span data-ttu-id="bd7fc-116">組織のロゴを追加したり、サポート用 web サイトと免責事項、およびテキストのみのフッターへのリンクなど、役に立つ情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bd7fc-116">You can add your organization's logo and include helpful information, such as links to your support website and legal disclaimer, and a text-only footer.</span></span> 

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a><span data-ttu-id="bd7fc-117">会議出席依頼のロゴを作成するためのヒント</span><span class="sxs-lookup"><span data-stu-id="bd7fc-117">Tips for creating a logo for meeting invitations</span></span>  

1. <span data-ttu-id="bd7fc-118">188 ピクセル 30 ピクセルの高さ (非常に小さいです) では、イメージを作成します。</span><span class="sxs-lookup"><span data-stu-id="bd7fc-118">Create an image that's no more than 188 pixels wide by 30 pixels tall (it's quite small).</span></span> 
2. <span data-ttu-id="bd7fc-119">イメージを JPG 形式で保存します。</span><span class="sxs-lookup"><span data-stu-id="bd7fc-119">Save the image in JPG format.</span></span> 
3. <span data-ttu-id="bd7fc-120">ネットワーク共有など、組織内のすべてのユーザーがアクセスできる中央の場所にイメージを格納します。</span><span class="sxs-lookup"><span data-stu-id="bd7fc-120">Store the image in a central location that everyone in your organization can access, such as a network share.</span></span> 

### <a name="customize-your-meeting-invitations"></a><span data-ttu-id="bd7fc-121">会議出席依頼をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="bd7fc-121">Customize your meeting invitations</span></span>

<span data-ttu-id="bd7fc-122">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**</span><span class="sxs-lookup"><span data-stu-id="bd7fc-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="bd7fc-123">左側のナビゲーションでは、**会議**に移動 > **会議を設定**します。</span><span class="sxs-lookup"><span data-stu-id="bd7fc-123">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
2. <span data-ttu-id="bd7fc-124">[**電子メール招待状**の場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bd7fc-124">Under **Email invitation**, do the following:</span></span> 

    <span data-ttu-id="bd7fc-125">![会議の設定-invitation.png](media/meeting-settings-invitation.png "のスクリーン ショットは、会議のチーム会議用にカスタマイズできる招待状の設定")</span><span class="sxs-lookup"><span data-stu-id="bd7fc-125">![meeting-settings-invitation.png](media/meeting-settings-invitation.png "Screen shot of the meeting invitation settings that you can customize for Teams meetings")</span></span> 

    - <span data-ttu-id="bd7fc-126">**ロゴの URL**ロゴを保存する場所の URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="bd7fc-126">**Logo URL** Enter the URL where your logo is stored.</span></span> 
    - <span data-ttu-id="bd7fc-127">**有効な URL**組織の法的な懸念事項を参照する有効な web サイトの場合は、ここに URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="bd7fc-127">**Legal URL** If your organization has a legal website that you want people to go to for any legal concerns, enter the URL here.</span></span> 
    - <span data-ttu-id="bd7fc-128">**URL のヘルプ**組織がサポートする web サイトに問題が発生する場合に移動するようにする場合は、ここに URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="bd7fc-128">**Help URL** If your organization has a support website that you want people to go to if they run into issues, enter the URL here.</span></span>
    - <span data-ttu-id="bd7fc-129">**フッター**フッターとして使用するテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="bd7fc-129">**Footer** Enter text that you want to include as a footer.</span></span> 
3. <span data-ttu-id="bd7fc-130">1 時間など、変更を伝達するを待ちます。</span><span class="sxs-lookup"><span data-stu-id="bd7fc-130">Wait an hour or so for the changes to propagate.</span></span> <span data-ttu-id="bd7fc-131">会議のチームに会議出席依頼は次のように参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd7fc-131">Then schedule a Teams meeting to see what the meeting invitation looks like.</span></span>  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a><span data-ttu-id="bd7fc-132">チームの会議のためのリアルタイムのメディア トラフィックを処理する方法を設定します。</span><span class="sxs-lookup"><span data-stu-id="bd7fc-132">Set how you want to handle real-time media traffic for Teams meetings</span></span>
<span data-ttu-id="bd7fc-133">サービスの品質 (QoS) を使用してネットワーク トラフィックの優先順位を設定する場合、QoS のマーカーを有効にすることができ、メディア トラフィックの種類ごとにポートの範囲を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="bd7fc-133">If you're using Quality of Service (QoS) to prioritize network traffic, you can enable QoS markers and you can set port ranges for each type of media traffic.</span></span> 

 <span data-ttu-id="bd7fc-134">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**</span><span class="sxs-lookup"><span data-stu-id="bd7fc-134">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="bd7fc-135">左側のナビゲーションでは、**会議**に移動 > **会議を設定**します。</span><span class="sxs-lookup"><span data-stu-id="bd7fc-135">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span> 
2. <span data-ttu-id="bd7fc-136">[**ネットワーク**では、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bd7fc-136">Under **Network**, do the following:</span></span>

    <span data-ttu-id="bd7fc-137">![会議の設定-network.png](media/meeting-settings-network.png "チーム会議は、マイクロソフトのチームの管理センターでのネットワーク設定のスクリーン ショット")</span><span class="sxs-lookup"><span data-stu-id="bd7fc-137">![meeting-settings-network.png](media/meeting-settings-network.png "Screen shot of the network settings for Teams meetings in the Microsoft Teams admin center")</span></span>

    - <span data-ttu-id="bd7fc-138">QoS のマーカーを有効にするには、**トラフィックのリアルタイム メディアの挿入のサービスの品質 (QoS) のマーカー**を入れます。</span><span class="sxs-lookup"><span data-stu-id="bd7fc-138">To enable QoS markers, turn on **Insert Quality of Service (QoS) markers for real-time media traffic**.</span></span>
    - <span data-ttu-id="bd7fc-139">**リアルタイム メディア トラフィックの種類ごとにポートの範囲を選択**すると、横には、ポート範囲を指定するのには**を指定するポートの範囲**を選択し、オーディオ、ビデオ、および画面共有の開始と終了のポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="bd7fc-139">To specify port ranges, next to **Select a port range for each type of real-time media traffic**, select  **Specify port ranges**, and then enter the starting and ending ports for audio, video, and screen sharing.</span></span> 
    
        <span data-ttu-id="bd7fc-140">**自動的にすべての利用可能なポートを使用して**1024 の間で利用可能なポートを選択すると、65535 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="bd7fc-140">If you select **Automatically use any available ports**, available ports between 1024 and 65535 are used.</span></span> 

 ### <a name="related-topics"></a><span data-ttu-id="bd7fc-141">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bd7fc-141">Related topics</span></span>
- [<span data-ttu-id="bd7fc-142">サービスの品質 (QoS のチームで)</span><span class="sxs-lookup"><span data-stu-id="bd7fc-142">Quality of Service (QoS) in Teams</span></span>](qos-in-teams.md)

