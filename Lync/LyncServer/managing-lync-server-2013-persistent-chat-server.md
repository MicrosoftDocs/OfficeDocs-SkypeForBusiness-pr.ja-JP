---
title: Lync Server 2013、常設チャット サーバーの管理
description: Lync Server 2013、常設チャットサーバーを管理する。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server 2013, Persistent Chat Server
ms:assetid: 82befdc6-5d32-45f1-bfd7-aaedffed1ab8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398657(v=OCS.15)
ms:contentKeyID: 48184672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe5306c79c738d61b70c3dd079fb55650e6fdae9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544583"
---
# <a name="managing-lync-server-2013-persistent-chat-server"></a><span data-ttu-id="f691e-103">Lync Server 2013、常設チャット サーバーの管理</span><span class="sxs-lookup"><span data-stu-id="f691e-103">Managing Lync Server 2013, Persistent Chat Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f691e-104">_**トピックの最終更新日:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="f691e-104">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="f691e-105">Lync Server 2013 の常設チャットサーバーを使用すると、複数のユーザーが、特定のトピック (テキスト、リンク、ファイルなど) に関するコンテンツを投稿してアクセスできるようにする会話に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="f691e-105">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="f691e-106">ユーザーはセッション中にリアルタイムで通信することができますが、各セッションの内容は永続的です。つまり、セッションが終了した後も引き続き利用可能であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="f691e-106">Although users can communicate in real time during a session, the content of each session is persistent, which means that it continues to be available after a session ends.</span></span>

<span data-ttu-id="f691e-107">常設チャットルームの内容は、主に短いテキストメッセージで構成されていますが、長いメッセージ ( *ストーリー*と呼ばれる) と、ハイパーリンク、絵文字、アップロードされたドキュメントも含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f691e-107">The content of Persistent Chat rooms consists primarily of short text messages, although it can include longer messages, referred to as *stories*, and also hyperlinks, emoticons, and uploaded documents.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f691e-108">ファイルのアップロードとダウンロードは、Lync 2013 クライアントではサポートされていません。ただし、Lync Server 2013 の常設チャットサーバーでは引き続きサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f691e-108">File upload and download is not supported by the Lync 2013 client; however, it is still supported by Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="f691e-109">従来のグループチャットクライアントはファイルを投稿および表示できますが、Lync 2013 クライアント経由で同じチャットルームにアクセスすると、ファイルにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="f691e-109">The legacy Group Chat client can post and view files, but if the same chat room is accessed via the Lync 2013 client, it will not be able to access the files.</span></span>



</div>

<span data-ttu-id="f691e-110">チャット ルームへのアクセスは、メンバーシップ一覧によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="f691e-110">Access to a chat room is controlled by a membership list.</span></span> <span data-ttu-id="f691e-111">どのメンバーも、チャット ルームの全履歴を時系列で確認したり、全文検索に使用したりできます。</span><span class="sxs-lookup"><span data-stu-id="f691e-111">The entire chat room history is available to any member for chronological review or full-text search.</span></span> <span data-ttu-id="f691e-112">常設チャットクライアントの使用の詳細については、「展開」のドキュメントの「計画」のドキュメントの「 [Lync server 2013 でのクライアント](lync-server-2013-planning-for-clients.md) とデバイスの展開」および「 [lync server 2013 でのクライアントとデバイスの展開](lync-server-2013-deploying-clients-and-devices.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f691e-112">For details about using the Persistent Chat client, see [Planning for clients in Lync Server 2013](lync-server-2013-planning-for-clients.md) in the Planning documentation, and [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

<span data-ttu-id="f691e-113">組織に常設チャットサーバーを設定するときは、展開時に初期構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="f691e-113">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="f691e-114">ただし、常設チャットサーバーのサポートの実装方法を変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f691e-114">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="f691e-115">たとえば、組織内の特定のチームまたはグループに対して、常設チャットサーバーのサポートとコントロールを設定する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f691e-115">For example, you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="f691e-116">このセクションでは、常設チャットサーバーの展開をカスタマイズするのに役立つ情報と手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="f691e-116">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="f691e-117">常設チャットサーバー用に構成できる機能の詳細については、「計画」のドキュメントの「 [Lync server 2013 での組織の要件の定義](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) 」および「計画」、「展開」、または「操作」のドキュメントの「 [lync server 2013 で](lync-server-2013-how-persistent-chat-server-works.md) の常設チャットサーバーの動作」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f691e-117">For details about the features and functionality that you can configure for Persistent Chat Server, see [Defining your organization's requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) in the Planning documentation, and [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="f691e-118">Lync Server 2013 用の常設チャットサーバーの展開の詳細については、「展開」のドキュメントの「展開, [常設チャットサーバーを Lync server 2013 に展開](lync-server-2013-deploying-persistent-chat-server.md) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f691e-118">For details about deploying Persistent Chat Server for Lync Server 2013, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f691e-119">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f691e-119">In This Section</span></span>

  - [<span data-ttu-id="f691e-120">Lync Server 2013 での常設チャットサーバーの動作</span><span class="sxs-lookup"><span data-stu-id="f691e-120">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="f691e-121">カテゴリを使用して常設チャットサーバーを管理する</span><span class="sxs-lookup"><span data-stu-id="f691e-121">Using categories to administer Persistent Chat Server</span></span>](using-categories-to-administer-persistent-chat-server.md)

  - [<span data-ttu-id="f691e-122">常設チャットのメンバーシップについて</span><span class="sxs-lookup"><span data-stu-id="f691e-122">Understanding Persistent Chat membership</span></span>](understanding-persistent-chat-membership.md)

  - [<span data-ttu-id="f691e-123">常設チャットサーバーのベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="f691e-123">Persistent Chat Server best practices</span></span>](persistent-chat-server-best-practices.md)

  - [<span data-ttu-id="f691e-124">Lync Server 2013 でのカテゴリ、ルーム、およびアドインの管理</span><span class="sxs-lookup"><span data-stu-id="f691e-124">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)

  - [<span data-ttu-id="f691e-125">Lync Server 2013 での常設チャットのユーザーアクセスの管理</span><span class="sxs-lookup"><span data-stu-id="f691e-125">Managing Persistent Chat user access in Lync Server 2013</span></span>](lync-server-2013-managing-persistent-chat-user-access.md)

  - [<span data-ttu-id="f691e-126">Lync Server 2013 での常設チャットシステムの運用と保守</span><span class="sxs-lookup"><span data-stu-id="f691e-126">Operating and maintaining the Persistent Chat system in Lync Server 2013</span></span>](lync-server-2013-operating-and-maintaining-the-persistent-chat-system.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

