---
title: "Microsoft Teams ユーザーまたはチームに訴訟ホールドを適用する"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: "セキュリティ/コンプライアンス センターを使用した Microsoft Teams のユーザーまたはチームへの訴訟ホールドの適用と、データ要件に基づいて訴訟ホールドを適用する必要のある項目について説明します。"
appliesto:
- Microsoft Teams
ms.openlocfilehash: 66dbf943c34c095db39b9b5399f44872c28d583e
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2018
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a><span data-ttu-id="7323e-103">Microsoft Teams ユーザーまたはチームに訴訟ホールドを適用する</span><span class="sxs-lookup"><span data-stu-id="7323e-103">Place a Microsoft Teams user or team on legal hold</span></span>
==================================================

<span data-ttu-id="7323e-p101">ユーザーまたはチームに訴訟ホールドを適用するには、[セキュリティ/コンプライアンス センター](https://go.microsoft.com/fwlink/?linkid=854628)に移動します。新しいケースを作成すると、メールボックスまたはサイトのいずれかをホールドするオプションが提示されます。</span><span class="sxs-lookup"><span data-stu-id="7323e-p101">To put a user or a team on Legal Hold, navigate to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=854628). When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

> [!NOTE]
> <span data-ttu-id="7323e-106">ユーザーをホールドしてもグループは自動的にホールドされません。その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="7323e-106">Placing a user on hold does not automatically place a group on hold or vice-versa.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7323e-107">ユーザーまたはグループにホールドを適用すると、すべてのメッセージのコピーが保持されます。</span><span class="sxs-lookup"><span data-stu-id="7323e-107">“When a user or group is placed on hold, all message copies will be retained.</span></span> <span data-ttu-id="7323e-108">たとえば、Clay さんがチャネルにメッセージを投稿し、そのメッセージを変更したとします。</span><span class="sxs-lookup"><span data-stu-id="7323e-108">Example: Clay posted a message in a channel and then modified the message.</span></span> <span data-ttu-id="7323e-109">ホールドのシナリオでは、これら両方のメッセージのコピーが保持されます。</span><span class="sxs-lookup"><span data-stu-id="7323e-109">In a hold scenario, both copies of the message are retained.</span></span> <span data-ttu-id="7323e-110">訴訟ホールドなしでは、最新のメッセージのみが保持されます。</span><span class="sxs-lookup"><span data-stu-id="7323e-110">Without Legal Hold, only the latest message is retained.</span></span>



<span data-ttu-id="7323e-111">次の図は Clay さんに関する調査を示しています。</span><span class="sxs-lookup"><span data-stu-id="7323e-111">In the figure below, there is an investigation involving Clay.</span></span> <span data-ttu-id="7323e-112">Clay さんは Brokers-Dealers チームのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="7323e-112">Clay is a member of the Brokers-Dealers team.</span></span>

<span data-ttu-id="7323e-113">Clay さんがブローカー業務の計画について話したと考えられるすべての場所に対して訴訟ホールドを適用する必要がある場合は、チームの SharePoint サイト、Clay さんの OneDrive for Business サイトを訴訟ホールド対象サイトのリストに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7323e-113">If we needed to Legal Hold all the places Clay could have discussed Brokering plans, ensure that the team’s SharePoint site is added to the Legal Hold site list, as well as Clay’s OneDrive for Business site.</span></span>

![[新しいルール/ポリシー リストの作成] ダイアログ ボックスのスクリーンショット。](media/Place_a_Microsoft_Teams_user_or_team_on_legal_hold_image3.png)

<span data-ttu-id="7323e-115">データ要件に応じて訴訟ホールドを適用する必要のある項目を理解するには、次の表を使用してください。</span><span class="sxs-lookup"><span data-stu-id="7323e-115">To recap, use the table below to understand what needs to be placed on Legal Hold based on data requirements:</span></span>

|<span data-ttu-id="7323e-116">シナリオ</span><span class="sxs-lookup"><span data-stu-id="7323e-116">Scenario</span></span>  |<span data-ttu-id="7323e-117">ホールドを適用する項目</span><span class="sxs-lookup"><span data-stu-id="7323e-117">What to place on hold</span></span>  |
|---------|---------|
|<span data-ttu-id="7323e-118">**Microsoft Teams プライベート チャット**</span><span class="sxs-lookup"><span data-stu-id="7323e-118">**Microsoft Teams Private Chats**</span></span>     |<span data-ttu-id="7323e-119">ユーザーのメールボックス</span><span class="sxs-lookup"><span data-stu-id="7323e-119">User mailbox</span></span>         |
|<span data-ttu-id="7323e-120">**Microsoft Teams チャネル チャット**</span><span class="sxs-lookup"><span data-stu-id="7323e-120">**Microsoft Teams Channel Chats**</span></span>    |<span data-ttu-id="7323e-121">チームで使用するグループ メールボックス</span><span class="sxs-lookup"><span data-stu-id="7323e-121">Group mailbox used for the team</span></span>         |
|<span data-ttu-id="7323e-122">**Microsoft Teams コンテンツ (例: Wiki、ファイル)**</span><span class="sxs-lookup"><span data-stu-id="7323e-122">**Microsoft Teams Content (e.g. Wiki, Files)**</span></span>     |<span data-ttu-id="7323e-123">チームが使用する SharePoint サイト</span><span class="sxs-lookup"><span data-stu-id="7323e-123">SharePoint site used by the team</span></span>         |
|<span data-ttu-id="7323e-124">**プライベートなコンテンツ**</span><span class="sxs-lookup"><span data-stu-id="7323e-124">**Private Content**</span></span>     |<span data-ttu-id="7323e-125">ユーザーの OneDrive for Business サイト</span><span class="sxs-lookup"><span data-stu-id="7323e-125">OneDrive for Business site of the user</span></span>         |
