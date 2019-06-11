---
title: 'Lync Server 2013: 常設チャット サーバーの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Persistent Chat Server
ms:assetid: 23f7c886-304d-495a-ae70-3cbb44241acd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425717(v=OCS.15)
ms:contentKeyID: 48183622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a744f4eb251bbbacc8b1b5f4c2a5978a9689f225
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="1e0f5-102">Lync Server 2013 の常設チャット サーバーの概要</span><span class="sxs-lookup"><span data-stu-id="1e0f5-102">Overview of Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e0f5-103">_**最終更新日:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="1e0f5-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="1e0f5-104">Lync Server 2013 の常設チャットサーバーを使用すると、ユーザーはマルチパーティのトピックベースの会話に参加することができます。これにより、時間の経過と共に維持されます。</span><span class="sxs-lookup"><span data-stu-id="1e0f5-104">Lync Server 2013, Persistent Chat Server enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="1e0f5-105">常設チャットサーバーは、組織が次のことを行うのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1e0f5-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="1e0f5-106">地理的に分散したチームと部門を越えたチーム間のコミュニケーションを向上させます。</span><span class="sxs-lookup"><span data-stu-id="1e0f5-106">Improve communication between geographically dispersed and cross-functional teams.</span></span> <span data-ttu-id="1e0f5-107">常設チャットを使用すると、チームは情報、アイデア、意思決定を効率的に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1e0f5-107">By using Persistent Chat, teams can efficiently share information, ideas, and decisions with one another.</span></span> <span data-ttu-id="1e0f5-108">チャットルーム (ディスカッションフォーラム) に投稿されたメッセージは保持 (つまり、時間を経て利用可能になることがあります) できるので、複数の場所や部門のユーザーが同時にオンラインでない場合でも、参加することができます。</span><span class="sxs-lookup"><span data-stu-id="1e0f5-108">The messages posted to chat rooms (discussion forums) can persist (that is, can be available over time), so that people from different locations and departments can participate, even when they are not simultaneously online.</span></span> <span data-ttu-id="1e0f5-109">ユーザーがチャットルームに接続している場合は、チャットルームにバックチャット (構成可能な数のチャット履歴メッセージ) が自動的に読み込まれ、会話のコンテキストがユーザーに与えられます。</span><span class="sxs-lookup"><span data-stu-id="1e0f5-109">When a user connects to a chat room, backchat (a configurable number of chat-history messages) is automatically loaded in the chat room to give the user a context for the conversation.</span></span>

  - <span data-ttu-id="1e0f5-110">情報の認識が向上します。</span><span class="sxs-lookup"><span data-stu-id="1e0f5-110">Improve information awareness.</span></span> <span data-ttu-id="1e0f5-111">クライアント側のフィルターを使用することで、ユーザーはメッセージの内容内のキーワードやメッセージの "差出人" フィールドの値などの条件を定義して、常設チャットのインスタントメッセージまたはチャットルームメッセージでそれらの条件が満たされた場合に通知を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="1e0f5-111">By using client-side filters, users can define conditions—such as keywords in message content, or the value of the "from" field in a message—to receive notification when those conditions are met in Persistent Chat instant messages or chat room messages.</span></span> <span data-ttu-id="1e0f5-112">こうすることで、ユーザーは最も興味のあるコンテンツを常に最新の状態に保つことができます。</span><span class="sxs-lookup"><span data-stu-id="1e0f5-112">This way, users can stay up-to-date with the content that interests them most.</span></span>

  - <span data-ttu-id="1e0f5-113">拡張組織とのコミュニケーションを向上させます。</span><span class="sxs-lookup"><span data-stu-id="1e0f5-113">Improve communication with their extended organization.</span></span> <span data-ttu-id="1e0f5-114">組織内の他のユーザーとの長期間のトピックでの共同作業を容易にしたり、情報を共有するための永続的な場所を提供したりすることで、常設チャットでコミュニケーションを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="1e0f5-114">By making it easy to collaborate over long-running topics with others in the organization, and by providing a persistent place to share information, Persistent Chat helps improve communication.</span></span>

  - <span data-ttu-id="1e0f5-115">情報のオーバーロードを減らします。</span><span class="sxs-lookup"><span data-stu-id="1e0f5-115">Reduce information overload.</span></span> <span data-ttu-id="1e0f5-116">ユーザーは、クライアント側のフィルターを使用して、興味のあるチャットルームとメッセージをフォローできます。また、フォローするチャットルームを連絡先リストに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="1e0f5-116">Users can follow chat rooms and messages of most interest by using client-side filters, and can add chat rooms they want to follow to their contact list.</span></span>

  - <span data-ttu-id="1e0f5-117">重要な知識と情報の分散を増やします。</span><span class="sxs-lookup"><span data-stu-id="1e0f5-117">Increase dispersion of important knowledge and information.</span></span> <span data-ttu-id="1e0f5-118">すべてのチームがアクセスできるように、ドキュメントやリンクをスレッド内に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1e0f5-118">Documents and links can be included within conversations for access by all the team.</span></span> <span data-ttu-id="1e0f5-119">より広範なチームに質問を投稿することで、ユーザーは、分野の専門家による回答を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="1e0f5-119">By posting questions to a broader team, users can benefit from responses by subject matter experts.</span></span> <span data-ttu-id="1e0f5-120">他の情報システムとの統合により、組織の重要なデータを大きなグループに簡単に伝えることができます。</span><span class="sxs-lookup"><span data-stu-id="1e0f5-120">Integration with other information systems enables important organizational data to be easily communicated to large groups.</span></span>

<span data-ttu-id="1e0f5-121">Lync Server 2013 でチャットルームを有効にするには、Lync Server 2013 常設チャットを展開します。</span><span class="sxs-lookup"><span data-stu-id="1e0f5-121">To enable chat rooms in Lync Server 2013, deploy Lync Server 2013 Persistent Chat.</span></span> <span data-ttu-id="1e0f5-122">チャットルームを有効にする方法については、の<http://go.microsoft.com/fwlink/p/?linkid=270945>常設チャットのヘルプをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1e0f5-122">For information about enabling chat rooms, see the Persistent Chat Help at <http://go.microsoft.com/fwlink/p/?linkid=270945>.</span></span> <span data-ttu-id="1e0f5-123">ユーザーが Lync Server を有効にしていて、Lync Server のサポートが展開されている場合、ユーザーは Lync 2013 常設チャットをインストールして使用し、チャットルームのサポートを提供できます。</span><span class="sxs-lookup"><span data-stu-id="1e0f5-123">If users are enabled for Lync Server, and Lync Server support is deployed, users can install and use Lync 2013 Persistent Chat to provide chat room support.</span></span>

<span data-ttu-id="1e0f5-124">組織でコンプライアンスの規則に従う必要がある場合は、必要に応じて常設チャットのコンプライアンスサービスを展開できます。</span><span class="sxs-lookup"><span data-stu-id="1e0f5-124">If your organization is required to follow compliance regulations, you can optionally deploy Persistent Chat Compliance service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

