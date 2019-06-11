---
title: Lync Server 2013 会議のユーザーモデル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: The conferencing user model
ms:assetid: ba4bbba9-f2e3-4cab-8eba-b51f12133cab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205199(v=OCS.15)
ms:contentKeyID: 48185229
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d4e8f55a9538c9cb70847bc090680662047b6ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840461"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-conferencing-user-model-in-lync-server-2013"></a><span data-ttu-id="2bc69-102">Lync Server 2013 の会議ユーザーモデル</span><span class="sxs-lookup"><span data-stu-id="2bc69-102">The conferencing user model in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bc69-103">_**最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="2bc69-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="2bc69-104">Lync Server 会議のユーザーモデルの重要な部分は、会議のサイズです。</span><span class="sxs-lookup"><span data-stu-id="2bc69-104">A critical part of the Lync Server conferencing user model is meeting size.</span></span> <span data-ttu-id="2bc69-105">(前のセクションで説明したように) 複数のデータポイントからデータを収集した後、次のことを決定しました。</span><span class="sxs-lookup"><span data-stu-id="2bc69-105">After collecting data from the multiple data points (as described in the previous section), we determined the following:</span></span>

  - <span data-ttu-id="2bc69-106">ほとんどの会議は、実際にはわずか 4 ~ 6 人の参加者が開催する、共同作業の小さな会議です。</span><span class="sxs-lookup"><span data-stu-id="2bc69-106">Most meetings are actually small collaborative meetings with an average of four to six participants</span></span>

  - <span data-ttu-id="2bc69-107">会議の約 80% は、参加者が20人を超えています。</span><span class="sxs-lookup"><span data-stu-id="2bc69-107">Approximately 80 percent of meetings have fewer than 20 participants.</span></span>

  - <span data-ttu-id="2bc69-108">会議の 99.98% は、参加者数が100を超えています。</span><span class="sxs-lookup"><span data-stu-id="2bc69-108">99.98 percent of meetings have fewer than 100 participants.</span></span>

<span data-ttu-id="2bc69-109">会議のサイズに加えて、会議のユーザーモデルでは、次のようなさまざまな要因も考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bc69-109">In addition to meeting size, the conferencing user model also takes into account a variety of factors, such as:</span></span>

  - <span data-ttu-id="2bc69-110">**同時会議**   では、同時に複数のユーザーが会議に出席することが予想されますか?</span><span class="sxs-lookup"><span data-stu-id="2bc69-110">**Concurrent meetings**   How many users are expected to be in meetings at the same time?</span></span>

  - <span data-ttu-id="2bc69-111">**メディアミックス**   会議のユーザーによって使用されるメディアの種類。</span><span class="sxs-lookup"><span data-stu-id="2bc69-111">**Media mix**   What types of media are available and expected to be used by users in meetings?</span></span>

  - <span data-ttu-id="2bc69-112">**ユーザーの種類**   は、内部ユーザー、リモートユーザー、フェデレーションユーザー、匿名ユーザーですか。</span><span class="sxs-lookup"><span data-stu-id="2bc69-112">**User types**   Are users internal users, remote users, federated users, or anonymous users?</span></span>

  - <span data-ttu-id="2bc69-113">**会議のランプアップ**   会議のすべてのユーザーが会議に参加するにはどのくらいの時間がかかりますか?</span><span class="sxs-lookup"><span data-stu-id="2bc69-113">**Meeting ramp up time**   How long does it take for all users of a meeting to join a meeting?</span></span>

<span data-ttu-id="2bc69-114">ユーザーモデルの詳細については、「 [Lync Server 2013 のユーザーモデル](lync-server-2013-user-models.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bc69-114">For details about the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="2bc69-115">テストに使用する会議とユーザーの数を決定するには、次の操作を行いました。</span><span class="sxs-lookup"><span data-stu-id="2bc69-115">To determine the number of meetings and users to use for testing, we did the following:</span></span>

  - <span data-ttu-id="2bc69-116">組織内のユーザーの合計数を取得しました (たとえば、8万ユーザー)。会議の同時実行率 (たとえば、すべてのユーザーの 5%) によって、同時に会議に参加していると予想されるユーザーの合計数 (この例では、5% のユーザー) を求めています。、4000ユーザー)。</span><span class="sxs-lookup"><span data-stu-id="2bc69-116">Took the total number of users in an organization (for example, 80,000 users) and multiplied it by the meeting concurrency rate (for example, 5% of all users) to determine the total number of users expected to be in meetings at the same time (in this example, 4000 users).</span></span>

  - <span data-ttu-id="2bc69-117">フロントエンドサーバーあたりの会議出席者の推定数 (この例では、フロントエンドサーバーあたり500ユーザー) を決定するために、ユーザーの合計数を、展開の Lync Server 2013、フロントエンドサーバー (たとえば、8台) で割ります。</span><span class="sxs-lookup"><span data-stu-id="2bc69-117">Divided the total number of users by the number of Lync Server 2013, Front End Servers in the deployment (for example, 8 servers) to determine the estimated number of meeting participants per Front End Server (in this example, 500 users per Front End Server).</span></span>

  - <span data-ttu-id="2bc69-118">フロントエンドサーバーあたりのユーザー数を平均会議のサイズ (たとえば、4人のユーザー) で割って、フロントエンドサーバーあたりの会議の推定平均数 (この例では、フロントエンドサーバーあたり125会議) を決定します。</span><span class="sxs-lookup"><span data-stu-id="2bc69-118">Divided the number of users per Front End Server by the average meeting size (for example, 4 users) to determine the estimated average number of meetings per Front End Server (in this example, 125 meetings per Front End Server).</span></span>

  - <span data-ttu-id="2bc69-119">各フロントエンドサーバーでメディアのロードを1つずつ取得するために、メディアミックスを見積もりました。</span><span class="sxs-lookup"><span data-stu-id="2bc69-119">To get the per media load on each Front End Server, we estimated the media mix.</span></span> <span data-ttu-id="2bc69-120">たとえば、会議の 75% が必要なのは、音声サポートだけでなく、会議の 50% ではアプリケーション共有が必要であると想定した場合、47会議と188ユーザーは、各フロントエンドサーバーに同時に接続して、アプリケーション共有を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2bc69-120">For example, assuming that 75% of the meetings require more than just audio support and 50% of those meetings require application sharing, an average of 47 meetings and 188 users connect concurrently to each Front End Server for application sharing.</span></span>

  - <span data-ttu-id="2bc69-121">サーバーのスケーラビリティを確保するために、さまざまな会議サイズ (共有プールの最大250ユーザーのユーザーモデルに基づく) をテストしました。</span><span class="sxs-lookup"><span data-stu-id="2bc69-121">Tested a variety of meeting sizes (based our user model of up to 250 users in a shared pool) to ensure server scalability.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

