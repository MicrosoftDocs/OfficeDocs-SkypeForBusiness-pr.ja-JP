---
title: Lync Server 2013、常設チャット サーバーの管理
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
ms.openlocfilehash: 067e24a7e1534e355e39f80b6a3fda90e059be14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-persistent-chat-server"></a><span data-ttu-id="8450e-102">Lync Server 2013、常設チャット サーバーの管理</span><span class="sxs-lookup"><span data-stu-id="8450e-102">Managing Lync Server 2013, Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8450e-103">_**最終更新日:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="8450e-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="8450e-104">Lync Server 2013 の常設チャットサーバーを使用して、複数のユーザーが、テキスト、リンク、ファイルなどの特定のトピックに関するコンテンツを投稿してアクセスできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="8450e-104">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="8450e-105">ユーザーはセッション中にリアルタイムで通信することができますが、各セッションのコンテンツは永続的であり、セッションが終了した後も引き続き利用可能であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="8450e-105">Although users can communicate in real time during a session, the content of each session is persistent, which means that it continues to be available after a session ends.</span></span>

<span data-ttu-id="8450e-106">常設チャットルームの内容は、主に短いテキストメッセージで構成されていますが、*ストーリー*と呼ばれる長いメッセージと、ハイパーリンク、絵文字、アップロードされたドキュメントにも含めることができます。</span><span class="sxs-lookup"><span data-stu-id="8450e-106">The content of Persistent Chat rooms consists primarily of short text messages, although it can include longer messages, referred to as *stories*, and also hyperlinks, emoticons, and uploaded documents.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8450e-107">ファイルのアップロードとダウンロードは Lync 2013 クライアントでサポートされていません。ただし、引き続き Lync Server 2013 の常設チャットサーバーでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8450e-107">File upload and download is not supported by the Lync 2013 client; however, it is still supported by Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="8450e-108">従来のグループチャットクライアントでは、ファイルの投稿と表示はできますが、Lync 2013 クライアント経由で同じチャットルームにアクセスした場合、ファイルにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8450e-108">The legacy Group Chat client can post and view files, but if the same chat room is accessed via the Lync 2013 client, it will not be able to access the files.</span></span>



</div>

<span data-ttu-id="8450e-109">チャットルームへのアクセスは、メンバーシップリストによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="8450e-109">Access to a chat room is controlled by a membership list.</span></span> <span data-ttu-id="8450e-110">チャットルームの履歴全体は、時系列レビューまたはフルテキスト検索のいずれかのメンバーが利用できます。</span><span class="sxs-lookup"><span data-stu-id="8450e-110">The entire chat room history is available to any member for chronological review or full-text search.</span></span> <span data-ttu-id="8450e-111">常設チャットクライアントの使用について詳しくは、「計画ドキュメントの[Lync server 2013 でのクライアントの計画](lync-server-2013-planning-for-clients.md)」をご覧ください。展開ドキュメントの[lync server 2013 でクライアントとデバイスを展開](lync-server-2013-deploying-clients-and-devices.md)してください。</span><span class="sxs-lookup"><span data-stu-id="8450e-111">For details about using the Persistent Chat client, see [Planning for clients in Lync Server 2013](lync-server-2013-planning-for-clients.md) in the Planning documentation, and [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

<span data-ttu-id="8450e-112">組織に常設チャットサーバーを設定する場合は、展開時に初期構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="8450e-112">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="8450e-113">ただし、常設チャットサーバーサポートの実装方法を変更する必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="8450e-113">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="8450e-114">たとえば、組織内の特定のチームまたはグループに対して、常設チャットサーバーのサポートとコントロールを設定する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="8450e-114">For example, you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="8450e-115">このセクションには、常設チャットサーバーの展開をカスタマイズするための情報と手順が記載されています。</span><span class="sxs-lookup"><span data-stu-id="8450e-115">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="8450e-116">常設チャットサーバー用に構成できる機能の詳細については、計画ドキュメントの「 [Lync server 2013 での常設チャットサーバーに関する組織の要件の定義](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md)」と「計画ドキュメント、展開ドキュメント、または運用ドキュメント」の「 [lync server 2013 での常設チャットサーバーの動作](lync-server-2013-how-persistent-chat-server-works.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8450e-116">For details about the features and functionality that you can configure for Persistent Chat Server, see [Defining your organization's requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) in the Planning documentation, and [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="8450e-117">Lync Server 2013 用の常設チャットサーバーの展開について詳しくは、展開ドキュメントの「 [Lync server 2013 での常設チャットサーバーの展開](lync-server-2013-deploying-persistent-chat-server.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8450e-117">For details about deploying Persistent Chat Server for Lync Server 2013, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8450e-118">このセクション中</span><span class="sxs-lookup"><span data-stu-id="8450e-118">In This Section</span></span>

  - [<span data-ttu-id="8450e-119">Lync Server 2013 での常設チャットサーバーの動作方法</span><span class="sxs-lookup"><span data-stu-id="8450e-119">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="8450e-120">カテゴリを使用して常設チャット サーバーを管理する</span><span class="sxs-lookup"><span data-stu-id="8450e-120">Using categories to administer Persistent Chat Server</span></span>](using-categories-to-administer-persistent-chat-server.md)

  - [<span data-ttu-id="8450e-121">常設チャットのメンバーシップについて</span><span class="sxs-lookup"><span data-stu-id="8450e-121">Understanding Persistent Chat membership</span></span>](understanding-persistent-chat-membership.md)

  - [<span data-ttu-id="8450e-122">常設チャット サーバーのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="8450e-122">Persistent Chat Server best practices</span></span>](persistent-chat-server-best-practices.md)

  - [<span data-ttu-id="8450e-123">Lync Server 2013 でのカテゴリ、ルーム、およびアドインの管理</span><span class="sxs-lookup"><span data-stu-id="8450e-123">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)

  - [<span data-ttu-id="8450e-124">Lync Server 2013 での常設チャットのユーザー アクセスの管理</span><span class="sxs-lookup"><span data-stu-id="8450e-124">Managing Persistent Chat user access in Lync Server 2013</span></span>](lync-server-2013-managing-persistent-chat-user-access.md)

  - [<span data-ttu-id="8450e-125">Lync Server 2013 での常設チャット システムの運用および保守</span><span class="sxs-lookup"><span data-stu-id="8450e-125">Operating and maintaining the Persistent Chat system in Lync Server 2013</span></span>](lync-server-2013-operating-and-maintaining-the-persistent-chat-system.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

