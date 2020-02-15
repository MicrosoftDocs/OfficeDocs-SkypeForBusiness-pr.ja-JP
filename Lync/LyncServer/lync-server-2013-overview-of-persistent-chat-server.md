---
title: 'Lync Server 2013: 常設チャットサーバーの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Persistent Chat Server
ms:assetid: 23f7c886-304d-495a-ae70-3cbb44241acd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425717(v=OCS.15)
ms:contentKeyID: 48183622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab73f99c8b5818a68b232e2f2dd928f79d5ff094
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="ae885-102">Lync Server 2013 の常設チャットサーバーの概要</span><span class="sxs-lookup"><span data-stu-id="ae885-102">Overview of Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae885-103">_**トピックの最終更新日:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="ae885-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="ae885-104">Lync Server 2013、常設チャットサーバーを使用すると、ユーザーは、時間の経過とともに保持するマルチパーティのトピックベースの会話に参加できます。</span><span class="sxs-lookup"><span data-stu-id="ae885-104">Lync Server 2013, Persistent Chat Server enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="ae885-105">常設チャットサーバーは、組織が次のことを行えるように支援します。</span><span class="sxs-lookup"><span data-stu-id="ae885-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="ae885-106">地理的に分散されたチームや職能上の枠を越えたチーム間でのコミュニケーションを深めます。</span><span class="sxs-lookup"><span data-stu-id="ae885-106">Improve communication between geographically dispersed and cross-functional teams.</span></span> <span data-ttu-id="ae885-107">永続的なチャットを使用することで、teams は情報、アイデア、意思決定を互いに効率よく共有できます。</span><span class="sxs-lookup"><span data-stu-id="ae885-107">By using Persistent Chat, teams can efficiently share information, ideas, and decisions with one another.</span></span> <span data-ttu-id="ae885-108">チャットルーム (ディスカッションフォーラム) に投稿されたメッセージは保持 (つまり、いつでも利用できます) することができるので、異なる場所や部署のユーザーが同時にオンラインになっていない場合でも、参加することができます。</span><span class="sxs-lookup"><span data-stu-id="ae885-108">The messages posted to chat rooms (discussion forums) can persist (that is, can be available over time), so that people from different locations and departments can participate, even when they are not simultaneously online.</span></span> <span data-ttu-id="ae885-109">ユーザーがチャットルームに接続すると、バックチャット (構成可能な数のチャット履歴メッセージ) が自動的にチャットルームに読み込まれ、会話のコンテキストをユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="ae885-109">When a user connects to a chat room, backchat (a configurable number of chat-history messages) is automatically loaded in the chat room to give the user a context for the conversation.</span></span>

  - <span data-ttu-id="ae885-110">情報の認知を高めます。</span><span class="sxs-lookup"><span data-stu-id="ae885-110">Improve information awareness.</span></span> <span data-ttu-id="ae885-111">クライアント側のフィルターを使用すると、ユーザーはメッセージの内容内のキーワード、メッセージの "差出人" フィールドの値などの条件を定義して、常設チャットのインスタントメッセージまたはチャットルームメッセージで条件が満たされたときに通知を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="ae885-111">By using client-side filters, users can define conditions—such as keywords in message content, or the value of the "from" field in a message—to receive notification when those conditions are met in Persistent Chat instant messages or chat room messages.</span></span> <span data-ttu-id="ae885-112">このようにすると、ユーザーは最も関心があるコンテンツを常に最新の状態に保つことができます。</span><span class="sxs-lookup"><span data-stu-id="ae885-112">This way, users can stay up-to-date with the content that interests them most.</span></span>

  - <span data-ttu-id="ae885-113">組織外の人間とのコミュニケーションを深めます。</span><span class="sxs-lookup"><span data-stu-id="ae885-113">Improve communication with their extended organization.</span></span> <span data-ttu-id="ae885-114">長期にわたって実行されているトピックを組織内の他のユーザーと簡単に共同作業し、情報を共有するための永続的な場所を提供することにより、常設チャットはコミュニケーションの向上に役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="ae885-114">By making it easy to collaborate over long-running topics with others in the organization, and by providing a persistent place to share information, Persistent Chat helps improve communication.</span></span>

  - <span data-ttu-id="ae885-115">情報過多を緩和します。</span><span class="sxs-lookup"><span data-stu-id="ae885-115">Reduce information overload.</span></span> <span data-ttu-id="ae885-116">ユーザーは、クライアント側のフィルターを使用して、興味のあるチャットルームとメッセージをフォローすることができます。また、フォローするチャットルームを連絡先リストに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="ae885-116">Users can follow chat rooms and messages of most interest by using client-side filters, and can add chat rooms they want to follow to their contact list.</span></span>

  - <span data-ttu-id="ae885-117">重要な知識と情報の分散を促進します。</span><span class="sxs-lookup"><span data-stu-id="ae885-117">Increase dispersion of important knowledge and information.</span></span> <span data-ttu-id="ae885-118">会話の中にドキュメントとリンクを含めて、チーム全体がアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="ae885-118">Documents and links can be included within conversations for access by all the team.</span></span> <span data-ttu-id="ae885-119">幅広い範囲のチームに質問を投げかけることで、ユーザーは、問題の領域の専門家から回答を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="ae885-119">By posting questions to a broader team, users can benefit from responses by subject matter experts.</span></span> <span data-ttu-id="ae885-120">その他の情報システムとの統合により、重要な組織データを大きなグループに簡単に伝達できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ae885-120">Integration with other information systems enables important organizational data to be easily communicated to large groups.</span></span>

<span data-ttu-id="ae885-121">Lync Server 2013 でチャットルームを有効にするには、「Lync Server 2013 常設チャット」を展開します。</span><span class="sxs-lookup"><span data-stu-id="ae885-121">To enable chat rooms in Lync Server 2013, deploy Lync Server 2013 Persistent Chat.</span></span> <span data-ttu-id="ae885-122">チャットルームの有効化の詳細については、の常設<http://go.microsoft.com/fwlink/p/?linkid=270945>チャットのヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae885-122">For information about enabling chat rooms, see the Persistent Chat Help at <http://go.microsoft.com/fwlink/p/?linkid=270945>.</span></span> <span data-ttu-id="ae885-123">ユーザーが Lync Server に対して有効になっており、Lync Server のサポートが展開されている場合、ユーザーは Lync 2013 常設チャットをインストールして使用してチャットルームサポートを提供できます。</span><span class="sxs-lookup"><span data-stu-id="ae885-123">If users are enabled for Lync Server, and Lync Server support is deployed, users can install and use Lync 2013 Persistent Chat to provide chat room support.</span></span>

<span data-ttu-id="ae885-124">組織が法令遵守規制に従う必要がある場合は、オプションで常設チャットコンプライアンスサービスを展開できます。</span><span class="sxs-lookup"><span data-stu-id="ae885-124">If your organization is required to follow compliance regulations, you can optionally deploy Persistent Chat Compliance service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

