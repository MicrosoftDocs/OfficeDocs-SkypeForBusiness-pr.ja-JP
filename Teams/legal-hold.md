---
title: "Microsoft Teams ユーザーまたはチームに訴訟ホールドを適用する | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "セキュリティ/コンプライアンス センターを使用した Microsoft Teams のユーザーまたはチームへの訴訟ホールドの適用と、データ要件に基づいて訴訟ホールドを適用する必要のある項目について説明します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: e400731545efb103aa0b6b865eef833238b4b154
ms.sourcegitcommit: 9756856140ea56a94e986c134c5c04e53e5c0fa6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2017
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a><span data-ttu-id="35ff6-103">Microsoft Teams ユーザーまたはチームに訴訟ホールドを適用する</span><span class="sxs-lookup"><span data-stu-id="35ff6-103">Place a Microsoft Teams user or team on legal hold</span></span>
==================================================

<span data-ttu-id="35ff6-p101">ユーザーまたはチームに訴訟ホールドを適用するには、[セキュリティ/コンプライアンス センター](https://go.microsoft.com/fwlink/?linkid=854628)に移動します。新しいケースを作成すると、メールボックスまたはサイトのいずれかをホールドするオプションが提示されます。</span><span class="sxs-lookup"><span data-stu-id="35ff6-p101">To put a user or a team on Legal Hold, navigate to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=854628). When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

|||
|---------|---------|
|![注意アイコン。](media/Place_a_Microsoft_Teams_user_or_team_on_legal_hold_image1.png)<br></br> <span data-ttu-id="35ff6-107">注意</span><span class="sxs-lookup"><span data-stu-id="35ff6-107">Note</span></span>     |<span data-ttu-id="35ff6-108">ユーザーをホールドしてもグループは自動的にホールドされません。その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="35ff6-108">Placing a user on hold does not automatically place a group on hold or vice-versa.</span></span>         |
|![重要アイコン。](media/Place_a_Microsoft_Teams_user_or_team_on_legal_hold_image2.png)<br></br> <span data-ttu-id="35ff6-110">重要</span><span class="sxs-lookup"><span data-stu-id="35ff6-110">Important</span></span>     |<span data-ttu-id="35ff6-111">ユーザーまたはグループにホールドを適用すると、すべてのメッセージのコピーが保持されます。</span><span class="sxs-lookup"><span data-stu-id="35ff6-111">When a user or group is placed on hold, all message copies will be retained.</span></span> <span data-ttu-id="35ff6-112">たとえば、Clay さんがチャネルにメッセージを投稿し、そのメッセージを変更したとします。</span><span class="sxs-lookup"><span data-stu-id="35ff6-112">Example: Clay posted a message in a channel and then modified the message.</span></span> <span data-ttu-id="35ff6-113">ホールドのシナリオでは、これら両方のメッセージのコピーが保持されます。</span><span class="sxs-lookup"><span data-stu-id="35ff6-113">In a hold scenario, both copies of the message are retained.</span></span> <span data-ttu-id="35ff6-114">訴訟ホールドなしでは、最新のメッセージのみが保持されます。</span><span class="sxs-lookup"><span data-stu-id="35ff6-114">Without Legal Hold, only the latest message is retained.</span></span>         |

<span data-ttu-id="35ff6-115">次の図は Clay さんに関する調査を示しています。</span><span class="sxs-lookup"><span data-stu-id="35ff6-115">In the figure below, there is an investigation involving Clay.</span></span> <span data-ttu-id="35ff6-116">Clay さんは Brokers-Dealers チームのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="35ff6-116">Clay is a member of the Brokers-Dealers team.</span></span>

<span data-ttu-id="35ff6-117">Clay さんがブローカー業務の計画について話したと考えられるすべての場所に対して訴訟ホールドを適用する必要がある場合は、チームの SharePoint サイト、Clay さんの OneDrive for Business サイトを訴訟ホールド対象サイトのリストに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35ff6-117">If we needed to Legal Hold all the places Clay could have discussed Brokering plans, ensure that the team’s SharePoint site is added to the Legal Hold site list, as well as Clay’s OneDrive for Business site.</span></span>

![[新しいルール/ポリシー リストの作成] ダイアログ ボックスのスクリーンショット。](media/Place_a_Microsoft_Teams_user_or_team_on_legal_hold_image3.png)

<span data-ttu-id="35ff6-119">データ要件に応じて訴訟ホールドを適用する必要のある項目を理解するには、次の表を使用してください。</span><span class="sxs-lookup"><span data-stu-id="35ff6-119">To recap, use the table below to understand what needs to be placed on Legal Hold based on data requirements:</span></span>

|<span data-ttu-id="35ff6-120">シナリオ</span><span class="sxs-lookup"><span data-stu-id="35ff6-120">Scenario</span></span>  |<span data-ttu-id="35ff6-121">ホールドを適用する項目</span><span class="sxs-lookup"><span data-stu-id="35ff6-121">What to place on hold</span></span>  |
|---------|---------|
|<span data-ttu-id="35ff6-122">**Microsoft Teams プライベート チャット**</span><span class="sxs-lookup"><span data-stu-id="35ff6-122">**Microsoft Teams Private Chats**</span></span>     |<span data-ttu-id="35ff6-123">ユーザーのメールボックス</span><span class="sxs-lookup"><span data-stu-id="35ff6-123">User mailbox</span></span>         |
|<span data-ttu-id="35ff6-124">**Microsoft Teams チャネル チャット**</span><span class="sxs-lookup"><span data-stu-id="35ff6-124">**Microsoft Teams Channel Chats**</span></span>    |<span data-ttu-id="35ff6-125">チームで使用するグループ メールボックス</span><span class="sxs-lookup"><span data-stu-id="35ff6-125">Group mailbox used for the team</span></span>         |
|<span data-ttu-id="35ff6-126">**Microsoft Teams コンテンツ (例: Wiki、ファイル)**</span><span class="sxs-lookup"><span data-stu-id="35ff6-126">**Microsoft Teams Content (e.g. Wiki, Files)**</span></span>     |<span data-ttu-id="35ff6-127">チームが使用する SharePoint サイト</span><span class="sxs-lookup"><span data-stu-id="35ff6-127">SharePoint site used by the team</span></span>         |
|<span data-ttu-id="35ff6-128">**プライベートなコンテンツ**</span><span class="sxs-lookup"><span data-stu-id="35ff6-128">**Private Content**</span></span>     |<span data-ttu-id="35ff6-129">ユーザーの OneDrive for Business サイト</span><span class="sxs-lookup"><span data-stu-id="35ff6-129">OneDrive for Business site of the user</span></span>         |
