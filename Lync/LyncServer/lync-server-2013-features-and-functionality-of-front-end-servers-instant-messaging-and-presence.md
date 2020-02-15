---
title: 'Lync Server 2013: フロントエンドサーバー、インスタントメッセージング、およびプレゼンスの特徴と機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Features and functionality of Front End Servers, instant messaging, and presence
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398109(v=OCS.15)
ms:contentKeyID: 48183294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8e25a74dcffe76f16b12a8c80f8ad8f980370dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="c0469-102">Lync Server 2013 のフロントエンドサーバー、インスタントメッセージング、およびプレゼンスの特徴と機能</span><span class="sxs-lookup"><span data-stu-id="c0469-102">Features and functionality of Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0469-103">_**トピックの最終更新日:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="c0469-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="c0469-104">フロントエンドサーバーは、ほとんどの Lync Server 機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="c0469-104">Front End Servers provide most Lync Server functionality.</span></span> <span data-ttu-id="c0469-105">次の2つのエディションがあります。 Lync Server Enterprise Edition は、主に大規模な組織向けに設計されており、主に小規模の組織向けに設計されており、小規模のハードウェア investement を必要とします。高可用性が必要です。</span><span class="sxs-lookup"><span data-stu-id="c0469-105">There are two editions available: Lync Server Enterprise Edition, which is designed primarily for larger organizations, and Lync Server Standard Edition, which is designed primarily for smaller organizations which want a smaller hardware investement and do not require high availability.</span></span> <span data-ttu-id="c0469-106">両方のエディションは、IM、プレゼンス、会議、エンタープライズ Voip などのすべての Lync Server ワークロードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c0469-106">Both editions support all Lync Server workloads including IM, presence, conferencing, and Enterprise Voice.</span></span>

<span data-ttu-id="c0469-p102">インスタント メッセージング (IM) を使用すると、ユーザーは各自のコンピューターでテキスト ベースのメッセージを使用して、リアルタイムで相互通信を行うことができます。 2 パーティとマルチパーティの両方の IM セッションがサポートされています。 2 パーティの IM 会話の参加者は、3 番目の参加者をいつでも会話に追加できます。 この際には、会議機能をサポートするように会話ウィンドウが変更されます。</span><span class="sxs-lookup"><span data-stu-id="c0469-p102">Instant messaging (IM) enables your users to communicate with each other in real time on their computers using text-based messages. Both two-party and multiparty IM sessions are supported. A participant in a two-party IM conversation can add a third participant to the conversation at any time. When this happens, the Conversation window changes to support conferencing features.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="c0469-111">1対1の通信に関係する Lync および Communicator クライアントは、ピアツーピアと呼ばれることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="c0469-111">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="c0469-112">技術的には、2つのクライアントは1つの会話に、インスタントメッセージング multipoint control unit (IMMCU) を中央に持つ1つの会話と通信します。</span><span class="sxs-lookup"><span data-stu-id="c0469-112">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="c0469-113">IMMCU はフロントエンドサーバーのコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="c0469-113">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="c0469-114">必要な通信ワークフローに IMMCU を配置すると、フロントエンドサーバーが有効になっている通話詳細記録およびその他の機能を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c0469-114">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="c0469-115">クライアント上の動的送信元ポートからフロントエンドサーバーポート TLS/TCP/5061 への通信です (推奨トランスポート層セキュリティを使用していることを前提としています)。</span><span class="sxs-lookup"><span data-stu-id="c0469-115">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="c0469-116">設計上、Lync Server と IMMCU がアクティブで利用可能な場合にのみ、ピアツーピア通信 (およびマルチパーティ IM) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c0469-116">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<span data-ttu-id="c0469-117">プレゼンス\*\* は、ネットワーク上の他のユーザーの状態に関する情報をユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="c0469-117">*Presence* provides information to users about the status of other on the network.</span></span> <span data-ttu-id="c0469-118">ユーザーのプレゼンス状態からは、他のユーザーがそのユーザーに連絡してもよいかどうかや、連絡する場合にインスタント メッセージング、電話、および電子メールのどれを使用するかを判断するのに役立つ情報を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="c0469-118">A user’s presence status provides information to help others decide whether they should try to contact the user and whether to use instant messaging, phone, or email.</span></span> <span data-ttu-id="c0469-119">プレゼンスにより、可能な場合は即時に通信しやすくなりますが、ユーザーが会議中であるかどうかや、外出のために応答できない状況なのかに関する情報も提供されます。</span><span class="sxs-lookup"><span data-stu-id="c0469-119">Presence encourages instant communication when possible, but it also provides information about whether a user is in a meeting or out of the office, indicating that instant communication is not possible.</span></span> <span data-ttu-id="c0469-120">このプレゼンス状態は、Lync などのプレゼンスアイコンとして表示されます。これには、Microsoft Outlook メッセージングおよびコラボレーションクライアント、Microsoft SharePoint テクノロジ、microsoft Word、microsoft Excel スプレッドシートなどのその他のプレゼンスを認識するアプリケーションがあります。ソフトウェア.</span><span class="sxs-lookup"><span data-stu-id="c0469-120">This presence status is displayed as a presence icon in Lync and other presence-aware applications, including the Microsoft Outlook messaging and collaboration client, Microsoft SharePoint technologies, Microsoft Word, and Microsoft Excel spreadsheet software.</span></span> <span data-ttu-id="c0469-121">プレゼンス アイコンからは、そのユーザーの現在の状態と、連絡してもよいかどうかを判別できます。</span><span class="sxs-lookup"><span data-stu-id="c0469-121">The presence icon represents the user’s current availability and willingness to communicate.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

