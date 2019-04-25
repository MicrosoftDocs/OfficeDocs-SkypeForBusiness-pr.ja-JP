---
title: Microsoft Teams ユーザーまたはチームに訴訟ホールドを適用する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: セキュリティ/コンプライアンス センターを使用した Microsoft Teams のユーザーまたはチームへの訴訟ホールドの適用と、データ要件に基づいて訴訟ホールドを適用する必要のある項目について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: eec053649cedfa3e29738dd1679d88b43ee54770
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233047"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a><span data-ttu-id="90b49-103">Microsoft Teams ユーザーまたはチームに訴訟ホールドを適用する</span><span class="sxs-lookup"><span data-stu-id="90b49-103">Place a Microsoft Teams user or team on legal hold</span></span>
==================================================

<span data-ttu-id="90b49-p101">ユーザーまたはチームに訴訟ホールドを適用するには、[セキュリティ/コンプライアンス センター](https://go.microsoft.com/fwlink/?linkid=854628)に移動します。新しいケースを作成すると、メールボックスまたはサイトのいずれかをホールドするオプションが提示されます。</span><span class="sxs-lookup"><span data-stu-id="90b49-p101">To put a user or a team on Legal Hold, navigate to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=854628). When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

> [!NOTE]
> <span data-ttu-id="90b49-106">ユーザーをホールドしてもグループは自動的にホールドされません。その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="90b49-106">Placing a user on hold does not automatically place a group on hold or vice-versa.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="90b49-107">保留中のユーザーまたはグループが配置されると、すべてのメッセージのコピーが保持されます。</span><span class="sxs-lookup"><span data-stu-id="90b49-107">When a user or group is placed on hold, all message copies will be retained.</span></span> <span data-ttu-id="90b49-108">たとえば、Clay さんがチャネルにメッセージを投稿し、そのメッセージを変更したとします。</span><span class="sxs-lookup"><span data-stu-id="90b49-108">Example: Clay posted a message in a channel and then modified the message.</span></span> <span data-ttu-id="90b49-109">ホールドのシナリオでは、これら両方のメッセージのコピーが保持されます。</span><span class="sxs-lookup"><span data-stu-id="90b49-109">In a hold scenario, both copies of the message are retained.</span></span> <span data-ttu-id="90b49-110">訴訟ホールドなしでは、最新のメッセージのみが保持されます。</span><span class="sxs-lookup"><span data-stu-id="90b49-110">Without Legal Hold, only the latest message is retained.</span></span>



<span data-ttu-id="90b49-111">次の図は Clay さんに関する調査を示しています。</span><span class="sxs-lookup"><span data-stu-id="90b49-111">In the figure below, there is an investigation involving Clay.</span></span> <span data-ttu-id="90b49-112">Clay さんは Brokers-Dealers チームのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="90b49-112">Clay is a member of the Brokers-Dealers team.</span></span>

<span data-ttu-id="90b49-113">Clay さんがブローカー業務の計画について話したと考えられるすべての場所に対して訴訟ホールドを適用する必要がある場合は、チームの SharePoint サイト、Clay さんの OneDrive for Business サイトを訴訟ホールド対象サイトのリストに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90b49-113">If we needed to Legal Hold all the places Clay could have discussed Brokering plans, ensure that the team’s SharePoint site is added to the Legal Hold site list, as well as Clay’s OneDrive for Business site.</span></span>

![[新しいルール/ポリシー リストの作成] ダイアログ ボックスのスクリーンショット。](media/Place_a_Microsoft_Teams_user_or_team_on_legal_hold_image3.png)

<span data-ttu-id="90b49-115">データ要件に応じて訴訟ホールドを適用する必要のある項目を理解するには、次の表を使用してください。</span><span class="sxs-lookup"><span data-stu-id="90b49-115">To recap, use the table below to understand what needs to be placed on Legal Hold based on data requirements:</span></span>

|<span data-ttu-id="90b49-116">シナリオ</span><span class="sxs-lookup"><span data-stu-id="90b49-116">Scenario</span></span>  |<span data-ttu-id="90b49-117">ホールドを適用する項目</span><span class="sxs-lookup"><span data-stu-id="90b49-117">What to place on hold</span></span>  |
|---------|---------|
|<span data-ttu-id="90b49-118">**Microsoft Teams プライベート チャット**</span><span class="sxs-lookup"><span data-stu-id="90b49-118">**Microsoft Teams Private Chats**</span></span>     |<span data-ttu-id="90b49-119">ユーザーのメールボックス</span><span class="sxs-lookup"><span data-stu-id="90b49-119">User mailbox</span></span>         |
|<span data-ttu-id="90b49-120">**Microsoft Teams チャネル チャット**</span><span class="sxs-lookup"><span data-stu-id="90b49-120">**Microsoft Teams Channel Chats**</span></span>    |<span data-ttu-id="90b49-121">チームで使用するグループ メールボックス</span><span class="sxs-lookup"><span data-stu-id="90b49-121">Group mailbox used for the team</span></span>         |
|<span data-ttu-id="90b49-122">**Microsoft Teams コンテンツ (例: Wiki、ファイル)**</span><span class="sxs-lookup"><span data-stu-id="90b49-122">**Microsoft Teams Content (e.g. Wiki, Files)**</span></span>     |<span data-ttu-id="90b49-123">チームが使用する SharePoint サイト</span><span class="sxs-lookup"><span data-stu-id="90b49-123">SharePoint site used by the team</span></span>         |
|<span data-ttu-id="90b49-124">**プライベートなコンテンツ**</span><span class="sxs-lookup"><span data-stu-id="90b49-124">**Private Content**</span></span>     |<span data-ttu-id="90b49-125">ユーザーの OneDrive for Business サイト</span><span class="sxs-lookup"><span data-stu-id="90b49-125">OneDrive for Business site of the user</span></span>         |
