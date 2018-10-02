---
title: チームでのライブ イベントのポリシーを管理します。
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
f1keywords: ms.teamsadmincenter.liveevents.policies
description: チームのライブ イベントのポリシーを使用してライブ イベントを保持する組織のユーザーの設定を管理する方法について説明します。
ms.openlocfilehash: b02f8de8accd0baff5f87af8682eab486866acb5
ms.sourcegitcommit: 6447a3aa060452c8d6879524cd6a56aecf33b152
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "25354349"
---
# <a name="manage-live-events-policies-in-teams"></a><span data-ttu-id="2bf25-103">チームでのライブ イベントのポリシーを管理します。</span><span class="sxs-lookup"><span data-stu-id="2bf25-103">Manage live events policies in Teams</span></span>

<span data-ttu-id="2bf25-104">チームのライブ イベントのポリシーを使用して、ライブ イベントとイベントの作成で使用可能な機能を保持できる、組織内のユーザーを制御します。</span><span class="sxs-lookup"><span data-stu-id="2bf25-104">Teams live events policies are used to control who in your organization can hold live events and the features that are available in the events that they create.</span></span> <span data-ttu-id="2bf25-105">ポリシーを作成した後は、ユーザーまたは組織内のユーザーのグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2bf25-105">After you create a policy, assign it to a user or groups of users in your organization.</span></span> 

- <span data-ttu-id="2bf25-106">**名**これは、ライブ イベントの [ポリシー] ページに表示されるポリシーの名前です。</span><span class="sxs-lookup"><span data-stu-id="2bf25-106">**Name** This is the name of the policy that appears on the live events policies page.</span></span> <span data-ttu-id="2bf25-107">64 文字より長いまたはできない特殊な文字があります。</span><span class="sxs-lookup"><span data-stu-id="2bf25-107">It can't be longer than 64 characters or have any special characters.</span></span>  
- <span data-ttu-id="2bf25-108">**説明**ポリシーのわかりやすい説明を追加するのにには、これを使用します。</span><span class="sxs-lookup"><span data-stu-id="2bf25-108">**Description** Use this to add a friendly description for the policy.</span></span> 
- <span data-ttu-id="2bf25-109">**スケジュールを設定できるようにします。** この機能を有効には、組織のユーザーが作成し、チームでのライブ イベントのスケジュールを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="2bf25-109">**Allow scheduling** Turning this on lets users in your organization create and schedule live events in Teams.</span></span>  
- <span data-ttu-id="2bf25-110">**出席者の議事録を許可します。** この有効ライブ イベント参加者はリアルタイムのキャプションと、イベントの中で翻訳を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bf25-110">**Allow transcription for attendees** Turning this on enables live event attendees to see real-time captions and translation during the event.</span></span> 
- <span data-ttu-id="2bf25-111">**スケジュールされたライブ イベントに参加したことができます。**</span><span class="sxs-lookup"><span data-stu-id="2bf25-111">**Who can join scheduled live events**</span></span>
    - <span data-ttu-id="2bf25-112">**全員**ユーザーは、組織外のユーザーを含むすべての人に参加できるライブ イベントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="2bf25-112">**Everyone** Users can create live events that everyone, including people outside your organization, can attend.</span></span>  
    - <span data-ttu-id="2bf25-113">**組織内のすべてのユーザー**ユーザーは、組織内のユーザーのみが参加できるライブ イベントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="2bf25-113">**Everyone in the organization** Users can create live events that only people in your organization can attend.</span></span> 
    - <span data-ttu-id="2bf25-114">**特定のユーザーまたはグループ**ユーザーがその特定のユーザーだけにはライブ イベントの作成できるか、組織内のグループに参加できます。</span><span class="sxs-lookup"><span data-stu-id="2bf25-114">**Specific users or groups** Users can create live events that only specific users or groups in your organization can attend.</span></span> 
- <span data-ttu-id="2bf25-115">**設定を記録します。** この設定は、ライブのチーム会議では、クイック スタートのライブ イベントとも呼ばれるを使用して生成されるイベントにのみ適用できます。</span><span class="sxs-lookup"><span data-stu-id="2bf25-115">**Recording setting** This setting can only be applied to live events that are produced using Teams meetings, also known as quick start live events.</span></span>  
    - <span data-ttu-id="2bf25-116">**常に記録**ユーザーが作成したライブ イベントは、常に記録されます。</span><span class="sxs-lookup"><span data-stu-id="2bf25-116">**Always record** The live events created by users are always recorded.</span></span> <span data-ttu-id="2bf25-117">終了後、イベント、イベント チームのメンバーがレコーディングをダウンロードでき、参加者は、イベントを見ることができます。</span><span class="sxs-lookup"><span data-stu-id="2bf25-117">After the event is over, event team members can download the recording and attendees can watch the event.</span></span> 
    - <span data-ttu-id="2bf25-118">**記録しません。** ユーザーが作成したライブ イベントが記録されることはありません。</span><span class="sxs-lookup"><span data-stu-id="2bf25-118">**Never record** The live events created by users are never recorded.</span></span>
    - <span data-ttu-id="2bf25-119">**開催者がいないかを記録できます。** ユーザーは、ライブ イベントを記録するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="2bf25-119">**Organizer can record or not** Users can decide whether to record the live event.</span></span> <span data-ttu-id="2bf25-120">それが記録されている場合、イベント終了後、イベント チームのメンバーがレコーディングをダウンロードでき、参加者は、イベントを見ることができます。</span><span class="sxs-lookup"><span data-stu-id="2bf25-120">If it is recorded, after the event is over, event team members can download the recording and attendees can watch the event.</span></span> 

 ### <a name="related-topics"></a><span data-ttu-id="2bf25-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2bf25-121">Related topics</span></span>
- [<span data-ttu-id="2bf25-122">ライブ イベントをチームは何ですか。</span><span class="sxs-lookup"><span data-stu-id="2bf25-122">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="2bf25-123">チームのライブ イベントの計画</span><span class="sxs-lookup"><span data-stu-id="2bf25-123">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="2bf25-124">チームのライブ イベントを設定します。</span><span class="sxs-lookup"><span data-stu-id="2bf25-124">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="2bf25-125">チームのライブ イベントを構成します。</span><span class="sxs-lookup"><span data-stu-id="2bf25-125">Configure Teams live events</span></span>](configure-teams-live-events.md)
