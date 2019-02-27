---
title: 会議ポリシーを管理する
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.date: 02/25/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
f1keywords:
- ms.teamsadmincenter.meetingpolicies.overview
description: Teams で会議のポリシー設定を管理する方法について説明します。
ms.openlocfilehash: 412deb1e8d671b40fd574d72a68f9dad15281645
ms.sourcegitcommit: baca91b0e022a1d2b5a522ef749a97463d61f560
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/27/2019
ms.locfileid: "30302698"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="7d2d1-103">Teams での会議ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="7d2d1-103">Manage meeting policies in Teams</span></span>

<span data-ttu-id="7d2d1-104">ミーティングのポリシーは、組織内のユーザーによってスケジュールされている会議の参加者をミーティングに使用可能な機能の制御に使用されます。</span><span class="sxs-lookup"><span data-stu-id="7d2d1-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="7d2d1-105">ポリシーを作成し、変更を行い後、は、ポリシーに、ユーザーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="7d2d1-105">After you create a policy and make your changes, you can then assign users to the policy.</span></span> 

## <a name="here-are-the-settings-you-can-change-to-fit-your-organization"></a><span data-ttu-id="7d2d1-106">お客様の組織に適した変更を行うことができる設定は次のとおりです</span><span class="sxs-lookup"><span data-stu-id="7d2d1-106">Here are the settings you can change to fit your organization</span></span>
<span data-ttu-id="7d2d1-107"><a name="bkgeneral"></a></span><span class="sxs-lookup"><span data-stu-id="7d2d1-107"><a name="bkgeneral"> </a></span></span>

### <a name="new-meeting-policy-name-and-description"></a><span data-ttu-id="7d2d1-108">ポリシーの名前および説明の新しい会議出席</span><span class="sxs-lookup"><span data-stu-id="7d2d1-108">New meeting policy name and description</span></span>
   - <span data-ttu-id="7d2d1-109">**新しい会議ポリシー**[会議ポリシー] ページに表示されるポリシーの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="7d2d1-109">**New meeting policy** Change this to the name of the policy that will appear on the Meeting policies page.</span></span> <span data-ttu-id="7d2d1-110">名前は、特殊文字が含まれているか、64 文字より長くすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7d2d1-110">The name can't contain special characters or be longer than 64 characters.</span></span>
   - <span data-ttu-id="7d2d1-111">**説明**作成するポリシーのわかりやすい説明を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="7d2d1-111">**Description** You can add a friendly description for the policy you create.</span></span> <span data-ttu-id="7d2d1-112">これは、ユーザーのグループにポリシーを割り当てる場合に役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="7d2d1-112">This will be helpful if you want to assign a policy to a group of users.</span></span>

### <a name="general"></a><span data-ttu-id="7d2d1-113">General</span><span class="sxs-lookup"><span data-stu-id="7d2d1-113">General</span></span>
   - <span data-ttu-id="7d2d1-114">**会議の開始を許可** これをオンにすると、会議に参加するユーザーが [会議の開始] 機能を使用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="7d2d1-114">**Allow Meet Now** Turning this on will allow the Meet Now feature to be available to users that join meetings.</span></span>
   - <span data-ttu-id="7d2d1-115">**Outlook アドインを許可** これをオンにすると、ポリシーに割り当てられたユーザーが、会議をスケジュールするときに、Outlook アドインを利用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="7d2d1-115">**Allow the Outlook add-in** Turning this on will let users assigned to the policy have the Outlook add-in available when they schedule meetings.</span></span>
   - <span data-ttu-id="7d2d1-116">**チャネル会議のスケジュール設定を許可** これをオンにするとチャネル会議をスケジュール設定することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="7d2d1-116">**Allow Channel meeting scheduling** Turning this on will allow Channel Meeting scheduling.</span></span>
   - <span data-ttu-id="7d2d1-117">**プライベート会議のスケジュール設定を許可** これをオンにすると、会議に参加するユーザーがプライベート会議のスケジュールを設定することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="7d2d1-117">**Allow scheduling private meetings** Turning this on will allow users that join a meeting to schedule private meetings.</span></span>

<span data-ttu-id="7d2d1-118"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="7d2d1-118"></span></span>

### <a name="audio--video"></a><span data-ttu-id="7d2d1-119">オーディオとビデオ</span><span class="sxs-lookup"><span data-stu-id="7d2d1-119">Audio & video</span></span>
   - <span data-ttu-id="7d2d1-120">**トランスクリプションを許可** これをオンにすると、ユーザーは会議のトランスクリプションを利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="7d2d1-120">**Allow transcription** If you turn this on, transcription of the meeting will be available to users.</span></span>
   - <span data-ttu-id="7d2d1-121">**クラウド録音を許可** これをオンにすると、録音がクラウドに保存されるようになります。</span><span class="sxs-lookup"><span data-stu-id="7d2d1-121">**Allow cloud recording** Turning this on will allow recordings to be saved to the cloud.</span></span>
   - <span data-ttu-id="7d2d1-122">**IP ビデオを許可** これをオンにすると、会議中に IP ビデオを使用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="7d2d1-122">**Allow IP video** Turning this on will allow IP videos during meetings.</span></span>
   - <span data-ttu-id="7d2d1-123">**メディア ビット レート (KB)** 会議用のビット レートを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="7d2d1-123">**Media bit rate (KBs)** You can set the bit rate for meetings.</span></span> <span data-ttu-id="7d2d1-124">既定値は 50 MB です。</span><span class="sxs-lookup"><span data-stu-id="7d2d1-124">The default is 50 MB.</span></span>

<span data-ttu-id="7d2d1-125"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="7d2d1-125"></span></span>

### <a name="content-sharing"></a><span data-ttu-id="7d2d1-126">コンテンツ共有</span><span class="sxs-lookup"><span data-stu-id="7d2d1-126">Content sharing</span></span>
   - <span data-ttu-id="7d2d1-127">**画面共有モード** 画面共有モードを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="7d2d1-127">**Screen sharing mode** You can select the screen sharing mode.</span></span> <span data-ttu-id="7d2d1-128">ここでは、ポリシーに割り当てられたユーザーが利用することができる会議で使用される画面のサイズになります。</span><span class="sxs-lookup"><span data-stu-id="7d2d1-128">This will be the size of the screen that will be used during a meeting that a user assigned with the policy can use.</span></span>
   - <span data-ttu-id="7d2d1-129">**参加者が制御を付与したり要求したりすることを許可** これにより、会議のすべての参加者が画面共有の制御を付与したり要求したりすることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="7d2d1-129">**Allow a participant to give or request control** This allows all participants in a meeting to give and request control of screen sharing.</span></span>
   - <span data-ttu-id="7d2d1-130">**外部の参加者が制御を付与したり要求したりすることを許可** これにより、画面が共有されているときに外部の参加者 (お客様の組織に属していないユーザー) が会議の制御を付与したり要求したりすることが可能になります。</span><span class="sxs-lookup"><span data-stu-id="7d2d1-130">**Allow an external participant to give or request control** This allows an external (someone not part of your organziation) participant to give and request control of a meeting when the screen is being shared.</span></span>
   - <span data-ttu-id="7d2d1-131">**PowerPoint 共有を許可** これをオンにすると、会議をスケジュール設定するユーザーが会議中に PowerPoint スライド デッキを共有することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="7d2d1-131">**Allow PowerPoint sharing** If you turn this on, users that schedule meetings can share PowerPoint slide decks during a meeting.</span></span>
   - <span data-ttu-id="7d2d1-132">**ホワイトボードを許可** これをオンにすると、会議の参加者が会議中にホワイトボードを利用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="7d2d1-132">**Allow whiteboard** If you turn this on, the whiteboard will be available to meeting participants during a meeting.</span></span>
   - <span data-ttu-id="7d2d1-133">**共有メモを許可** これをオンにすると、会議の参加者が会議中にホワイトボードを利用することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="7d2d1-133">**Allow shared notes** If you turn this on, shared notes will be available to meeting participants during a meeting.</span></span>

<span data-ttu-id="7d2d1-134"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="7d2d1-134"></span></span>

### <a name="participants--guests"></a><span data-ttu-id="7d2d1-135">参加者とゲスト</span><span class="sxs-lookup"><span data-stu-id="7d2d1-135">Participants & guests</span></span>
   - <span data-ttu-id="7d2d1-136">**会議を開始するのには匿名ユーザーを許可します。** この設定がオフの場合は、会議を開始できますチームのアプリケーションでの会議に認証されたユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="7d2d1-136">**Allow anonymous users to start meetings** If this setting is off, then only someone who has been authenticated to the meeting with a Teams app can start the meeting.</span></span> <span data-ttu-id="7d2d1-137">オンの場合は、誰でも会議を開始することができます。</span><span class="sxs-lookup"><span data-stu-id="7d2d1-137">If it's on, then anyone can start the meeting.</span></span>
   - <span data-ttu-id="7d2d1-138">**ユーザーの自動承認** これがオフの場合、会議の参加者は、誰かが会議を開始するまでロビーに残されたままになります。.</span><span class="sxs-lookup"><span data-stu-id="7d2d1-138">**Automatically admit users** If you turn this off, then meeting participants will be left in the lobby until someone starts the meeting.</span></span> <span data-ttu-id="7d2d1-139">ミーティングに参加するミーティングの参加者が許可される場合、自動的にします。</span><span class="sxs-lookup"><span data-stu-id="7d2d1-139">If it's on, meeting participants will be allowed to join the meeting automatically.</span></span>


