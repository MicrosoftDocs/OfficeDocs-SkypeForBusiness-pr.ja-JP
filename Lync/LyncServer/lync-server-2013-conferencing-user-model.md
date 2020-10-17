---
title: Lync Server 2013 会議のユーザーモデル
description: Lync Server 2013 会議のユーザーモデル。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: The conferencing user model
ms:assetid: ba4bbba9-f2e3-4cab-8eba-b51f12133cab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205199(v=OCS.15)
ms:contentKeyID: 48185229
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 699f41303b82f4d8fd2864cbf1b29a1c601b826e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555983"
---
# <a name="the-conferencing-user-model-in-lync-server-2013"></a><span data-ttu-id="9d8bb-103">Lync Server 2013 の会議のユーザーモデル</span><span class="sxs-lookup"><span data-stu-id="9d8bb-103">The conferencing user model in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d8bb-104">_**トピックの最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="9d8bb-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="9d8bb-105">Lync Server 会議のユーザーモデルの重要な部分は、会議のサイズです。</span><span class="sxs-lookup"><span data-stu-id="9d8bb-105">A critical part of the Lync Server conferencing user model is meeting size.</span></span> <span data-ttu-id="9d8bb-106">(前のセクションで説明したように) 複数のデータ ポイントからデータを収集したところ、次のことが明らかになりました。</span><span class="sxs-lookup"><span data-stu-id="9d8bb-106">After collecting data from the multiple data points (as described in the previous section), we determined the following:</span></span>

  - <span data-ttu-id="9d8bb-107">ほとんどの会議は、実際には参加者が平均 4 ～ 6 人の小規模なグループ作業の会議です。</span><span class="sxs-lookup"><span data-stu-id="9d8bb-107">Most meetings are actually small collaborative meetings with an average of four to six participants</span></span>

  - <span data-ttu-id="9d8bb-108">会議の約 80% は参加者が 20 人未満です。</span><span class="sxs-lookup"><span data-stu-id="9d8bb-108">Approximately 80 percent of meetings have fewer than 20 participants.</span></span>

  - <span data-ttu-id="9d8bb-109">会議の 99.98 % は参加者が 100 人未満です。</span><span class="sxs-lookup"><span data-stu-id="9d8bb-109">99.98 percent of meetings have fewer than 100 participants.</span></span>

<span data-ttu-id="9d8bb-110">会議サイズに加えて、会議ユーザー モデルでは次のようなさまざまな要素も考慮します。</span><span class="sxs-lookup"><span data-stu-id="9d8bb-110">In addition to meeting size, the conferencing user model also takes into account a variety of factors, such as:</span></span>

  - <span data-ttu-id="9d8bb-111">**同時会議**    同時に会議に何人のユーザーがいると予想されるか。</span><span class="sxs-lookup"><span data-stu-id="9d8bb-111">**Concurrent meetings**   How many users are expected to be in meetings at the same time?</span></span>

  - <span data-ttu-id="9d8bb-112">**メディアミックス**    会議でユーザーが使用することが予想されるメディアの種類は何か。</span><span class="sxs-lookup"><span data-stu-id="9d8bb-112">**Media mix**   What types of media are available and expected to be used by users in meetings?</span></span>

  - <span data-ttu-id="9d8bb-113">**ユーザーの種類**    ユーザーは、内部ユーザー、リモートユーザー、フェデレーションユーザー、匿名ユーザーのいずれかですか。</span><span class="sxs-lookup"><span data-stu-id="9d8bb-113">**User types**   Are users internal users, remote users, federated users, or anonymous users?</span></span>

  - <span data-ttu-id="9d8bb-114">**会議のランプアップ時間**    会議のすべてのユーザーが会議に参加するのにどれくらいの時間がかかりますか?</span><span class="sxs-lookup"><span data-stu-id="9d8bb-114">**Meeting ramp up time**   How long does it take for all users of a meeting to join a meeting?</span></span>

<span data-ttu-id="9d8bb-115">ユーザーモデルの詳細については、「 [Lync Server 2013 のユーザーモデル](lync-server-2013-user-models.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d8bb-115">For details about the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="9d8bb-116">テストに使用する会議およびユーザーの数を決定するため、次のことを行いました。</span><span class="sxs-lookup"><span data-stu-id="9d8bb-116">To determine the number of meetings and users to use for testing, we did the following:</span></span>

  - <span data-ttu-id="9d8bb-117">組織内のユーザーの総数 (例: ユーザー数 80,000) を取得し、それに会議の同時割合 (例: すべてのユーザーの 5%) をかけて、会議に同時に参加すると予想されるユーザーの総数を決定しました (この例では、ユーザー数は 4000)。</span><span class="sxs-lookup"><span data-stu-id="9d8bb-117">Took the total number of users in an organization (for example, 80,000 users) and multiplied it by the meeting concurrency rate (for example, 5% of all users) to determine the total number of users expected to be in meetings at the same time (in this example, 4000 users).</span></span>

  - <span data-ttu-id="9d8bb-118">フロントエンドサーバーあたりの会議参加者の推定数 (この500例では、1台のフロントエンドサーバー) を決定するために、ユーザーの合計数を Lync Server 2013、展開内のフロントエンドサーバーの数 (たとえば、8台のサーバー) で割る。</span><span class="sxs-lookup"><span data-stu-id="9d8bb-118">Divided the total number of users by the number of Lync Server 2013, Front End Servers in the deployment (for example, 8 servers) to determine the estimated number of meeting participants per Front End Server (in this example, 500 users per Front End Server).</span></span>

  - <span data-ttu-id="9d8bb-119">フロントエンドサーバーあたりのユーザー数を平均会議のサイズ (たとえば、4ユーザー) で割ることにより、フロントエンドサーバーあたりの会議の推定平均数 (この例では、1つのフロントエンドサーバーあたり125会議) を決定します。</span><span class="sxs-lookup"><span data-stu-id="9d8bb-119">Divided the number of users per Front End Server by the average meeting size (for example, 4 users) to determine the estimated average number of meetings per Front End Server (in this example, 125 meetings per Front End Server).</span></span>

  - <span data-ttu-id="9d8bb-120">各フロントエンドサーバーでメディア負荷の数を取得するには、メディアミックスを見積もります。</span><span class="sxs-lookup"><span data-stu-id="9d8bb-120">To get the per media load on each Front End Server, we estimated the media mix.</span></span> <span data-ttu-id="9d8bb-121">たとえば、会議の75% が、音声サポートだけでなく、その会議の50% ではアプリケーション共有が必要であると仮定した場合、アプリケーション共有のために各フロントエンドサーバーに対して、平均47会議と188ユーザーが同時に接続されます。</span><span class="sxs-lookup"><span data-stu-id="9d8bb-121">For example, assuming that 75% of the meetings require more than just audio support and 50% of those meetings require application sharing, an average of 47 meetings and 188 users connect concurrently to each Front End Server for application sharing.</span></span>

  - <span data-ttu-id="9d8bb-122">(共有プールの最大ユーザー数 250 のユーザー モデルに基づいて) さまざまな会議サイズをテストし、サーバーの拡張性を確保しました。</span><span class="sxs-lookup"><span data-stu-id="9d8bb-122">Tested a variety of meeting sizes (based our user model of up to 250 users in a shared pool) to ensure server scalability.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

