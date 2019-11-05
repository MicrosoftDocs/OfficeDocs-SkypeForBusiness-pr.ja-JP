---
title: Microsoft Teams ユーザーまたはチームに訴訟ホールドを適用する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: セキュリティ/コンプライアンス センターを使用した Microsoft Teams のユーザーまたはチームへの訴訟ホールドの適用と、データ要件に基づいて訴訟ホールドを適用する必要のある項目について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 25bd8e235be79ed805a854cbda2b4947f1c1269b
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968038"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a><span data-ttu-id="5df78-103">Microsoft Teams ユーザーまたはチームに訴訟ホールドを適用する</span><span class="sxs-lookup"><span data-stu-id="5df78-103">Place a Microsoft Teams user or team on legal hold</span></span>
==================================================

<span data-ttu-id="5df78-p101">ユーザーまたはチームに訴訟ホールドを適用するには、[セキュリティ/コンプライアンス センター](https://go.microsoft.com/fwlink/?linkid=854628)に移動します。新しいケースを作成すると、メールボックスまたはサイトのいずれかをホールドするオプションが提示されます。</span><span class="sxs-lookup"><span data-stu-id="5df78-p101">To put a user or a team on Legal Hold, navigate to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=854628). When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

> [!NOTE]
> <span data-ttu-id="5df78-106">ユーザーをホールドしてもグループは自動的にホールドされません。その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="5df78-106">Placing a user on hold does not automatically place a group on hold or vice-versa.</span></span>

> [!NOTE]
> <span data-ttu-id="5df78-107">プライベートチャネルメッセージの法的保持の構成はまだサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="5df78-107">We don’t yet support configuration for legal hold of private channel messages.</span></span> <span data-ttu-id="5df78-108">プライベートチャネルで共有されているファイルの法的な保留はサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5df78-108">Legal hold of files shared in private channels is supported.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5df78-109">ユーザーまたはグループを保留にすると、すべてのメッセージのコピーが保持されます。</span><span class="sxs-lookup"><span data-stu-id="5df78-109">When a user or group is placed on hold, all message copies will be retained.</span></span> <span data-ttu-id="5df78-110">たとえば、Clay さんがチャネルにメッセージを投稿し、そのメッセージを変更したとします。</span><span class="sxs-lookup"><span data-stu-id="5df78-110">Example: Clay posted a message in a channel and then modified the message.</span></span> <span data-ttu-id="5df78-111">ホールドのシナリオでは、これら両方のメッセージのコピーが保持されます。</span><span class="sxs-lookup"><span data-stu-id="5df78-111">In a hold scenario, both copies of the message are retained.</span></span> <span data-ttu-id="5df78-112">訴訟ホールドなしでは、最新のメッセージのみが保持されます。</span><span class="sxs-lookup"><span data-stu-id="5df78-112">Without Legal Hold, only the latest message is retained.</span></span>

<span data-ttu-id="5df78-113">次の図は Clay さんに関する調査を示しています。</span><span class="sxs-lookup"><span data-stu-id="5df78-113">In the figure below, there is an investigation involving Clay.</span></span> <span data-ttu-id="5df78-114">Clay さんは Brokers-Dealers チームのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="5df78-114">Clay is a member of the Brokers-Dealers team.</span></span>

<span data-ttu-id="5df78-115">Clay さんがブローカー業務の計画について話したと考えられるすべての場所に対して訴訟ホールドを適用する必要がある場合は、チームの SharePoint サイト、Clay さんの OneDrive for Business サイトを訴訟ホールド対象サイトのリストに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5df78-115">If we needed to Legal Hold all the places Clay could have discussed Brokering plans, ensure that the team’s SharePoint site is added to the Legal Hold site list, as well as Clay’s OneDrive for Business site.</span></span>

![[新しいルール/ポリシー リストの作成] ダイアログ ボックスのスクリーンショット。](media/Place_a_Microsoft_Teams_user_or_team_on_legal_hold_image3.png)

<span data-ttu-id="5df78-117">データ要件に応じて訴訟ホールドを適用する必要のある項目を理解するには、次の表を使用してください。</span><span class="sxs-lookup"><span data-stu-id="5df78-117">To recap, use the table below to understand what needs to be placed on Legal Hold based on data requirements:</span></span>

|<span data-ttu-id="5df78-118">シナリオ</span><span class="sxs-lookup"><span data-stu-id="5df78-118">Scenario</span></span>  |<span data-ttu-id="5df78-119">ホールドを適用する項目</span><span class="sxs-lookup"><span data-stu-id="5df78-119">What to place on hold</span></span>  |
|---------|---------|
|<span data-ttu-id="5df78-120">**Microsoft Teams プライベート チャット**</span><span class="sxs-lookup"><span data-stu-id="5df78-120">**Microsoft Teams Private Chats**</span></span>     |<span data-ttu-id="5df78-121">ユーザーのメールボックス</span><span class="sxs-lookup"><span data-stu-id="5df78-121">User mailbox</span></span>         |
|<span data-ttu-id="5df78-122">**Microsoft Teams チャネル チャット**</span><span class="sxs-lookup"><span data-stu-id="5df78-122">**Microsoft Teams Channel Chats**</span></span>    |<span data-ttu-id="5df78-123">チームで使用するグループ メールボックス</span><span class="sxs-lookup"><span data-stu-id="5df78-123">Group mailbox used for the team</span></span>         |
|<span data-ttu-id="5df78-124">**Microsoft Teams コンテンツ (例: Wiki、ファイル)**</span><span class="sxs-lookup"><span data-stu-id="5df78-124">**Microsoft Teams Content (e.g. Wiki, Files)**</span></span>     |<span data-ttu-id="5df78-125">チームが使用する SharePoint サイト</span><span class="sxs-lookup"><span data-stu-id="5df78-125">SharePoint site used by the team</span></span>         |
|<span data-ttu-id="5df78-126">**プライベートなコンテンツ**</span><span class="sxs-lookup"><span data-stu-id="5df78-126">**Private Content**</span></span>     |<span data-ttu-id="5df78-127">ユーザーの OneDrive for Business サイト</span><span class="sxs-lookup"><span data-stu-id="5df78-127">OneDrive for Business site of the user</span></span>         |
