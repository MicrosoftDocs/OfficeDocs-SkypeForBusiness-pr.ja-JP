---
title: 'Lync Server 2013: 常設チャットサーバーのしくみ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Persistent Chat Server works
ms:assetid: 3d04e9a1-3f0c-458e-bcbe-d27c8c464276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ683096(v=OCS.15)
ms:contentKeyID: 49684643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d919d7c9d955355a45ebf3c05391204ca919a3fa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528174"
---
# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a><span data-ttu-id="6827e-102">Lync Server 2013 での常設チャットサーバーの動作</span><span class="sxs-lookup"><span data-stu-id="6827e-102">How Persistent Chat Server works in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6827e-103">_**トピックの最終更新日:** 2012-11-21_</span><span class="sxs-lookup"><span data-stu-id="6827e-103">_**Topic Last Modified:** 2012-11-21_</span></span>

<span data-ttu-id="6827e-104">Lync Server 2013、常設チャットサーバーを使用すると、時間の経過と共に持続するマルチパーティのトピックベースの会話に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="6827e-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="6827e-105">常設チャットサーバーは、組織が次のことを行えるように支援します。</span><span class="sxs-lookup"><span data-stu-id="6827e-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="6827e-106">地理的に分散されたチームや職能上の枠を越えたチーム間でのコミュニケーションを深めます。</span><span class="sxs-lookup"><span data-stu-id="6827e-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="6827e-107">情報を広めて参加の輪を広げます。</span><span class="sxs-lookup"><span data-stu-id="6827e-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="6827e-108">組織外の人間とのコミュニケーションを深めます。</span><span class="sxs-lookup"><span data-stu-id="6827e-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="6827e-109">情報過多を緩和します。</span><span class="sxs-lookup"><span data-stu-id="6827e-109">Reduce information overload</span></span>

  - <span data-ttu-id="6827e-110">情報の認知を高めます。</span><span class="sxs-lookup"><span data-stu-id="6827e-110">Improve information awareness</span></span>

  - <span data-ttu-id="6827e-111">重要な知識と情報の分散を促進します。</span><span class="sxs-lookup"><span data-stu-id="6827e-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="6827e-112">Lync Server 2013 では、オプションの役割として常設チャットサーバーを展開できます。</span><span class="sxs-lookup"><span data-stu-id="6827e-112">You can deploy Persistent Chat Server as an optional role with Lync Server 2013.</span></span> <span data-ttu-id="6827e-113">常設チャットサービスは専用プール上で実行され、常設チャットサーバープールは Lync Server プールによってメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="6827e-113">Persistent Chat services run on a dedicated pool, and a Persistent Chat Server pool depends on a Lync Server pool to route messages to it.</span></span> <span data-ttu-id="6827e-114">クライアントは、XCCOS (eXtensible Chat Communication Over SIP) を使用します。</span><span class="sxs-lookup"><span data-stu-id="6827e-114">Clients use eXtensible Chat Communication Over SIP (XCCOS).</span></span> <span data-ttu-id="6827e-115">Lync Server フロントエンドサーバーは、トラフィックを常設チャットサーバープールにルーティングするように構成されます。</span><span class="sxs-lookup"><span data-stu-id="6827e-115">The Lync Server Front End Servers are configured to route the traffic to a Persistent Chat Server pool.</span></span>

<div>

## <a name="high-level-architecture"></a><span data-ttu-id="6827e-116">アーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="6827e-116">High-Level Architecture</span></span>

<span data-ttu-id="6827e-117">次の図は、常設チャットサーバーのアーキテクチャとサービスの大まかな視点を示しています。</span><span class="sxs-lookup"><span data-stu-id="6827e-117">The following diagrams provide high-level perspectives of the Persistent Chat Server architecture and services.</span></span>

<span data-ttu-id="6827e-118">**常設チャット サーバーのアーキテクチャの概要**</span><span class="sxs-lookup"><span data-stu-id="6827e-118">**Persistent Chat Server High-Level Architecture**</span></span>

<span data-ttu-id="6827e-119">![常設チャットサーバーのアーキテクチャ。](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "常設チャットサーバーのアーキテクチャ。")</span><span class="sxs-lookup"><span data-stu-id="6827e-119">![Persistent Chat Server architecture.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Persistent Chat Server architecture.")</span></span>

<span data-ttu-id="6827e-120">**常設チャット サーバーのサービスの概要**</span><span class="sxs-lookup"><span data-stu-id="6827e-120">**Persistent Chat Server High-Level Services**</span></span>

<span data-ttu-id="6827e-121">![常設チャットサーバーのコンポーネント。](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "常設チャットサーバーのコンポーネント。")</span><span class="sxs-lookup"><span data-stu-id="6827e-121">![Persistent Chat Server components.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Persistent Chat Server components.")</span></span>

<span data-ttu-id="6827e-122">常設チャットサーバーのフロントエンドサーバーでは、次の2つのサービスが実行されます。</span><span class="sxs-lookup"><span data-stu-id="6827e-122">Two services run on the Persistent Chat Server Front End Servers:</span></span>

  - <span data-ttu-id="6827e-123">常設チャット (チャネル)</span><span class="sxs-lookup"><span data-stu-id="6827e-123">Persistent Chat (Channel)</span></span>

  - <span data-ttu-id="6827e-124">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="6827e-124">Compliance</span></span>

<div>

## <a name="persistent-chat-channel-service"></a><span data-ttu-id="6827e-125">常設チャット (チャネル) サービス</span><span class="sxs-lookup"><span data-stu-id="6827e-125">Persistent Chat (Channel) Service</span></span>

<span data-ttu-id="6827e-126">常設チャット (チャネル) サービスは、常設チャットサーバーを担うコアサービスです。</span><span class="sxs-lookup"><span data-stu-id="6827e-126">The Persistent Chat (Channel) service is the core service responsible for Persistent Chat Server.</span></span> <span data-ttu-id="6827e-127">このサービスには、次の機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="6827e-127">This service provides the following functions:</span></span>

  - <span data-ttu-id="6827e-128">受信メッセージを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="6827e-128">Accepts incoming messages</span></span>

  - <span data-ttu-id="6827e-129">常設チャットルーム内のオンライン参加者を登録して一覧表示する</span><span class="sxs-lookup"><span data-stu-id="6827e-129">Registers and lists online participants within a Persistent Chat room</span></span>

  - <span data-ttu-id="6827e-130">メッセージを他のチャネル サブスクライバーに再送信します。</span><span class="sxs-lookup"><span data-stu-id="6827e-130">Retransmits messages to other channel subscribers</span></span>

  - <span data-ttu-id="6827e-131">チャネル管理、チャット ルームへの招待、検索、および新しいコンテンツ通知のロジックを実装します。</span><span class="sxs-lookup"><span data-stu-id="6827e-131">Implements logic for channel management, chat room invitation, search, and new content notifications</span></span>

<span data-ttu-id="6827e-132">常設チャット (チャネル) サービスは、常設チャットストアを使用して、チャットルームのコンテンツや他のシステムメタデータ (承認ルールなど) を格納し、アクセスします。</span><span class="sxs-lookup"><span data-stu-id="6827e-132">The Persistent Chat (Channel) service stores and accesses chat room content and other system metadata (authorization rules, and so on) by using the Persistent Chat Store.</span></span> <span data-ttu-id="6827e-133">このサービスは、常設チャットファイルストア内のチャットルームにアップロードされるファイルを格納します。</span><span class="sxs-lookup"><span data-stu-id="6827e-133">This service stores files that are uploaded into chat rooms in the Persistent Chat File Store.</span></span>

</div>

<div>

## <a name="compliance-service"></a><span data-ttu-id="6827e-134">コンプライアンス サービス</span><span class="sxs-lookup"><span data-stu-id="6827e-134">Compliance Service</span></span>

<span data-ttu-id="6827e-135">コンプライアンスサービスは、常設チャットサーバーのオプションコンポーネントであり、チャットのコンテンツとイベントを常設チャットコンプライアンスストアにアーカイブする役割を担います。</span><span class="sxs-lookup"><span data-stu-id="6827e-135">The Compliance service is an optional component of Persistent Chat Server and is responsible for archiving chat content and events to the Persistent Chat Compliance Store.</span></span> <span data-ttu-id="6827e-136">常設チャットのアクティビティをアーカイブする必要がある規制が組織にある場合は、オプションの常設チャットコンプライアンスサービスを展開できます。</span><span class="sxs-lookup"><span data-stu-id="6827e-136">If your organization has regulations that require Persistent Chat activity to be archived, you can deploy the optional Persistent Chat Compliance service.</span></span> <span data-ttu-id="6827e-137">コンプライアンスサービスは、常設チャットプールの各常設チャットサーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="6827e-137">The Compliance service is installed on each Persistent Chat Server in a Persistent Chat pool.</span></span> <span data-ttu-id="6827e-138">構成されている場合、常設チャットサーバーのコンプライアンスは、ルームへの参加や退室、メッセージの投稿と読み取りなどのユーザーアクティビティを記録します。</span><span class="sxs-lookup"><span data-stu-id="6827e-138">When configured, Persistent Chat Server compliance records user activity such as joining and leaving rooms, and posting and reading of messages.</span></span> <span data-ttu-id="6827e-139">コンプライアンスサービスは、常設チャットコンプライアンスファイルストアにアーカイブする必要があるファイルを格納します。</span><span class="sxs-lookup"><span data-stu-id="6827e-139">The Compliance service stores files that need to be archived in the Persistent Chat Compliance File Store.</span></span>

</div>

<div>

## <a name="persistent-chat-web-services"></a><span data-ttu-id="6827e-140">常設チャット Web サービス</span><span class="sxs-lookup"><span data-stu-id="6827e-140">Persistent Chat Web Services</span></span>

<span data-ttu-id="6827e-141">Lync Server フロントエンドサーバーでは、インターネットインフォメーションサービス (IIS) に依存し、web コンポーネントとして実装されている2つのサービスが実行されます。</span><span class="sxs-lookup"><span data-stu-id="6827e-141">On the Lync Server Front End Servers, two services run that depend on Internet Information Services (IIS), and are implemented as web components:</span></span>

  - <span data-ttu-id="6827e-142">**ファイルのアップロード/ダウンロード用の常設チャット Web サービス** チャットルームからファイルを投稿および取得する責任があります。</span><span class="sxs-lookup"><span data-stu-id="6827e-142">**Persistent Chat Web Services for File Upload/Download** Responsible for posting and retrieving files from chat rooms.</span></span>

  - <span data-ttu-id="6827e-143">**チャットルーム管理用の常設チャット Web サービス** ユーザーにチャットルームを管理する機能を提供し、新しいチャットルームを作成する責任を負います。</span><span class="sxs-lookup"><span data-stu-id="6827e-143">**Persistent Chat Web Services for Chat Room Management** Responsible for providing users the ability to manage their chat rooms, and create new chat rooms.</span></span>

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a><span data-ttu-id="6827e-144">常設チャットサーバーの使用を開始するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="6827e-144">How Do I Start Using Persistent Chat Server?</span></span>

<span data-ttu-id="6827e-145">常設チャットサーバーは、Lync Server 2013 インフラストラクチャ内のオプションのサーバーの役割です。</span><span class="sxs-lookup"><span data-stu-id="6827e-145">Persistent Chat Server is an optional server role within the Lync Server 2013 infrastructure.</span></span> <span data-ttu-id="6827e-146">常設チャットサーバーの役割をインストールすると、管理者によってポリシーによって有効にされたすべてのユーザーは、Lync 2013 クライアントで常設チャットを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6827e-146">If you install the Persistent Chat Server role, any users who have been enabled through policy by an administrator can use Persistent Chat with the Lync 2013 client.</span></span>

<span data-ttu-id="6827e-147">常設チャットサーバーを展開する方法、およびユーザーがポリシーによって機能を活用できるようにする方法の詳細については、「 [Lync server 2013 に常設チャットサーバーを展開](lync-server-2013-deploying-persistent-chat-server.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6827e-147">For details about how to deploy Persistent Chat Server and enable users to leverage the capabilities by policy, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>

<span data-ttu-id="6827e-148">常設チャットサーバーの展開で設定を構成する方法の詳細については、「 [Lync server 2013 の常設チャットサーバーの展開](lync-server-2013-deploying-persistent-chat-server.md) 」および「 [lync Server 2013、常設チャットサーバーの管理](managing-lync-server-2013-persistent-chat-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6827e-148">For details about how to configure settings on your Persistent Chat Server deployment, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="6827e-149">Lync 2013 クライアントで常設チャットの機能を利用できるように、ポリシーによってユーザーを有効にする方法の詳細については、「 [Lync server 2013 に常設チャットサーバーを展開](lync-server-2013-deploying-persistent-chat-server.md) する」および「 [lync Server 2013、常設チャットサーバーを管理](managing-lync-server-2013-persistent-chat-server.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6827e-149">For details about how to enable users by policy such that they can leverage Persistent Chat functionality in Lync 2013 client, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="6827e-150">常設チャットのコンプライアンスを展開した場合は、コンプライアンスの設定を構成する方法の詳細について「 [Lync server 2013、常設チャットサーバーの管理](managing-lync-server-2013-persistent-chat-server.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6827e-150">If you deployed Persistent Chat compliance, see [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) for details about how to configure settings for compliance.</span></span>

</div>

<div>

## <a name="persistent-chat-call-flows"></a><span data-ttu-id="6827e-151">常設チャットの通話フロー</span><span class="sxs-lookup"><span data-stu-id="6827e-151">Persistent Chat Call Flows</span></span>

<span data-ttu-id="6827e-152">常設チャットクライアントは、XCCOS を使用して常設チャットサービスと通信します。</span><span class="sxs-lookup"><span data-stu-id="6827e-152">The Persistent Chat client communicates with the Persistent Chat service by using XCCOS.</span></span> <span data-ttu-id="6827e-153">次の手順では、サインイン プロセス、および標準のルームのサブスクリプションとメッセージ投稿シナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6827e-153">The following sequences describe the sign-in process and a typical room subscription and message post scenario.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="6827e-154">サインイン</span><span class="sxs-lookup"><span data-stu-id="6827e-154">Sign-in</span></span>

<span data-ttu-id="6827e-155">次のコールフロー図と手順は、サインインプロセスについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="6827e-155">The following call flow diagram and steps describe the sign-in process.</span></span>

<span data-ttu-id="6827e-156">**常設チャットクライアントサインインの呼び出しフロー**</span><span class="sxs-lookup"><span data-stu-id="6827e-156">**Persistent Chat Client Sign-in Call Flow**</span></span>

<span data-ttu-id="6827e-157">![常設チャットサーバーの呼び出しフローの図。](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "常設チャットサーバーの呼び出しフローの図。")</span><span class="sxs-lookup"><span data-stu-id="6827e-157">![Persistent Chat Server call flow diagram.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Persistent Chat Server call flow diagram.")</span></span>

1.  <span data-ttu-id="6827e-158">常設チャットクライアントは、まず SIP サブスクライブを送信して、サーバーからインバンドプロビジョニングドキュメントを取得します。</span><span class="sxs-lookup"><span data-stu-id="6827e-158">The Persistent Chat client first sends a SIP SUBSCRIBE to retrieve the in-band provisioning document from the server.</span></span> <span data-ttu-id="6827e-159">このドキュメントは、ユーザーに対して常設チャットが有効または無効になっているかどうか、および常設チャットサーバープールの SIP Uri の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="6827e-159">This document indicates if Persistent Chat is enabled or disabled for the user and the list of SIP URIs for the Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="6827e-160">常設チャットクライアントは、前の手順で取得した常設チャットサーバーの SIP URI に SIP INVITE メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="6827e-160">The Persistent Chat client sends a SIP INVITE message to the SIP URI of the Persistent Chat Server that it obtained in the previous step.</span></span> <span data-ttu-id="6827e-161">招待のシーケンスの後には、200 OK と ACK が続き、常設チャットクライアントは常設チャットサーバーエンドポイントを使用して SIP セッションを開いたことになりました。</span><span class="sxs-lookup"><span data-stu-id="6827e-161">The INVITE sequence is followed by 200 OK and ACK, and the Persistent Chat client has now opened a SIP session with a Persistent Chat Server endpoint.</span></span> <span data-ttu-id="6827e-162">その結果、常設チャットクライアントは、アクションを実行するようにサーバーに要求するチャットメッセージまたはコマンドのいずれかが含まれる SIP 情報メッセージを送信することによって、常設チャットサーバーと通信します。</span><span class="sxs-lookup"><span data-stu-id="6827e-162">Consequently, the Persistent Chat client communicates with Persistent Chat Server by sending SIP INFO messages that contain either chat messages or commands requesting the server to take an action.</span></span> <span data-ttu-id="6827e-163">これらのメッセージはすべて、200 OK または503サービスを利用できない (つまりサーバー負荷が重い場合)、応答されます。</span><span class="sxs-lookup"><span data-stu-id="6827e-163">All of these messages are acknowledged with either 200 OK or 503 Service Unavailable (that is, in the event of heavy server load).</span></span> <span data-ttu-id="6827e-164">クライアントが503応答を受信した場合は、メッセージを再試行します。</span><span class="sxs-lookup"><span data-stu-id="6827e-164">If the client receives a 503 response, it will retry the message.</span></span> <span data-ttu-id="6827e-165">(この例では、503応答は含まれません)。サーバーがメッセージまたはコマンドを受け入れ、200 OK を送信した場合は、別の SIP INFO メッセージの形式でクライアントに応答を提供します。</span><span class="sxs-lookup"><span data-stu-id="6827e-165">(This example does not include a 503 response.) If the server accepts the message or command and sends 200 OK, it provides a response to the client in the form of a separate SIP INFO message.</span></span> <span data-ttu-id="6827e-166">この応答には、元のコマンドへの参照が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6827e-166">This response includes a reference to the originating command.</span></span>

3.  <span data-ttu-id="6827e-167">常設チャットクライアントは、XCCOS **getserverinfo** コマンドを含む SIP 情報メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="6827e-167">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getserverinfo** command.</span></span> <span data-ttu-id="6827e-168">常設チャットサーバーは、常設チャットサービスの構成に関する情報を含む新しい SIP 情報メッセージで応答します。</span><span class="sxs-lookup"><span data-stu-id="6827e-168">Persistent Chat Server replies with a new SIP INFO message that contains information about the Persistent Chat service configuration.</span></span>

4.  <span data-ttu-id="6827e-169">常設チャットクライアントは、XCCOS **getassociations** コマンドを含む SIP 情報メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="6827e-169">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getassociations** command.</span></span> <span data-ttu-id="6827e-170">常設チャットサーバーは、ユーザーがメンバーになっている会議室のリストを含む新しい SIP INFO メッセージで応答します。</span><span class="sxs-lookup"><span data-stu-id="6827e-170">Persistent Chat Server replies with a new SIP INFO message that contains the list of rooms of which the user is a member.</span></span> <span data-ttu-id="6827e-171">常設チャットクライアントは、ユーザーが上司となっている会議室の一覧を取得するコマンドを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="6827e-171">The Persistent Chat client repeats the command to retrieve the list of rooms of which the user is a manager.</span></span>

5.  <span data-ttu-id="6827e-172">常設チャットクライアントは、「プレゼンス」ドキュメントからフォローされているルームのリストを取得します。ここでは、各後の部屋は、「roomSetting」カテゴリで表されます。</span><span class="sxs-lookup"><span data-stu-id="6827e-172">The Persistent Chat client gets the list of followed rooms from the "presence" document, where each followed room is represented by a "roomSetting" category.</span></span> <span data-ttu-id="6827e-173">すべてのフォロー対象ルームは、ルーム Uri のリストを含む XCCOS **bjoin** コマンドを含む1つの SIP INFO メッセージによって参加します。</span><span class="sxs-lookup"><span data-stu-id="6827e-173">All followed rooms are joined by a single SIP INFO message that contains the XCCOS **bjoin** command that contains the list of room URIs.</span></span> <span data-ttu-id="6827e-174">フォロー対象ルームの一覧はサーバー上に保持されるので、任意のコンピューター上のすべてのクライアントは、指定されたユーザー URI に対してフォローしているルームのリストと同じです。</span><span class="sxs-lookup"><span data-stu-id="6827e-174">Because the list of followed rooms is kept on the server, any client on any computer has the same list of followed rooms for the specified user URI.</span></span> <span data-ttu-id="6827e-175">また、常設チャットクライアントは、ローカルコンピューターのレジストリで開いているルームのリストを保持し (このオプションがユーザーによって有効になっている場合)、開いている各ルームの XCCOS **join** コマンドを含む SIP 情報メッセージを送信することによって、これらの各ルームをサインイン時に結合します。</span><span class="sxs-lookup"><span data-stu-id="6827e-175">The Persistent Chat client also keeps the list of opened rooms (if this option is enabled by the user) in the local computer registry, and joins each of these rooms at sign-in by sending a SIP INFO message that contains the XCCOS **join** command for each opened room.</span></span> <span data-ttu-id="6827e-176">このリストはレジストリに保持されるため、異なるコンピューター上で実行されている2台の常設チャットクライアントで異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6827e-176">Because this list is kept in the registry, it can be different on two Persistent Chat clients running on different computers.</span></span>

6.  <span data-ttu-id="6827e-177">参加している各会議室に対して、常設チャットクライアントは XCCOS **bccontext** コマンドを含む SIP 情報メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="6827e-177">For each room joined, the Persistent Chat client sends a SIP INFO message that contains the XCCOS **bccontext** command.</span></span> <span data-ttu-id="6827e-178">常設チャットサーバーは、ルーム内の最新のチャットメッセージを含む新しい SIP 情報メッセージで応答します。</span><span class="sxs-lookup"><span data-stu-id="6827e-178">Persistent Chat Server replies with a new SIP INFO message that contains the most recent chat message in the room.</span></span>

7.  <span data-ttu-id="6827e-179">常設チャットクライアントは、XCCOS **getinv** (つまり、招待を取得) コマンドを含む SIP 情報メッセージを送信して、クライアントがまだ表示されていない新しい会議室の招待を要求します。</span><span class="sxs-lookup"><span data-stu-id="6827e-179">The Persistent Chat client sends a SIP INFO message that contains a XCCOS **getinv** (that is, get invitation) command to request any new room invitations that the client has not yet seen.</span></span> <span data-ttu-id="6827e-180">別の SIP 情報メッセージでは、常設チャットサーバーはこれらのルームの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="6827e-180">In a separate SIP INFO message, Persistent Chat Server returns a list of those rooms.</span></span>

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a><span data-ttu-id="6827e-181">ルームを購読し、メッセージを投稿する</span><span class="sxs-lookup"><span data-stu-id="6827e-181">Subscribe to a Room and Post a Message</span></span>

<span data-ttu-id="6827e-182">次のコールフロー図と手順は、一般的な会議室のサブスクリプションとメッセージ投稿シナリオについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="6827e-182">The following call flow diagram and steps describe a typical room subscription and message post scenario.</span></span>

<span data-ttu-id="6827e-183">**常設チャットクライアントルームのサブスクリプションとメッセージ投稿の通話フロー**</span><span class="sxs-lookup"><span data-stu-id="6827e-183">**Persistent Chat Client Room Subscription and Message Posting Call Flow**</span></span>

<span data-ttu-id="6827e-184">![ルームのサブスクリプションとメッセージ投稿シナリオ。](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "ルームのサブスクリプションとメッセージ投稿シナリオ。")</span><span class="sxs-lookup"><span data-stu-id="6827e-184">![Room subscription and message post scenario.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Room subscription and message post scenario.")</span></span>

1.  <span data-ttu-id="6827e-185">常設チャットクライアントから、User1 が [ **チャットルームに参加する**] をクリックし、[ **検索**] をクリックして、いくつかの検索条件を入力します。</span><span class="sxs-lookup"><span data-stu-id="6827e-185">From the Persistent Chat client, User1 clicks **Join a Chat Room**, clicks **Search**, and then enters some search criteria.</span></span> <span data-ttu-id="6827e-186">常設チャットクライアントは、XCCOS **chansrch** (ルーム検索) コマンドを含む SIP 情報メッセージを検索条件と共に送信します。</span><span class="sxs-lookup"><span data-stu-id="6827e-186">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **chansrch** (room search) command, along with the search criteria.</span></span> <span data-ttu-id="6827e-187">常設チャットサーバーは、バックエンドデータベースに対してクエリを行い、検索条件を満たす利用可能なルームの一覧が含まれる新しい SIP 情報メッセージで応答します。</span><span class="sxs-lookup"><span data-stu-id="6827e-187">Persistent Chat Server queries the back-end database and replies in a new SIP INFO message that contains a list of available rooms that meet the search criteria.</span></span>

2.  <span data-ttu-id="6827e-188">User1 が自身が参加するチャット ルームを選択し、[**このルームをフォロー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6827e-188">User1 selects the chat room that he or she wants to join, and then clicks **Follow this room**.</span></span> <span data-ttu-id="6827e-189">常設チャットクライアントは、常設チャットサーバーに、XCCOS **join** コマンドと、ユーザーが選択したチャットルームのルーム ID を含む SIP 情報メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="6827e-189">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **join** command and the room ID of the chat room that the user selected.</span></span> <span data-ttu-id="6827e-190">常設チャットサーバーは、プロビジョニングデータを含む SIP 情報メッセージで応答します。</span><span class="sxs-lookup"><span data-stu-id="6827e-190">Persistent Chat Server replies with a SIP INFO message that contains the provisioning data.</span></span>

3.  <span data-ttu-id="6827e-191">常設チャットクライアントは、常設チャットサーバーに、XCCOS **bccontext** (backchat コンテキスト) コマンドを含む SIP 情報メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="6827e-191">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **bccontext** (backchat context) command.</span></span> <span data-ttu-id="6827e-192">常設チャットサーバーはチャットの履歴を取得し、それを別の SIP 情報メッセージで常設チャットクライアントに返します。</span><span class="sxs-lookup"><span data-stu-id="6827e-192">Persistent Chat Server retrieves the chat history, and returns it to the Persistent Chat client in a separate SIP INFO message.</span></span> <span data-ttu-id="6827e-193">この時点で、ユーザーはチャット ルームに入り、いつでも参加することができます。</span><span class="sxs-lookup"><span data-stu-id="6827e-193">At this point, the user enters the chat room and is ready to participate.</span></span>

4.  <span data-ttu-id="6827e-194">User1 が新しいメッセージを入力し、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6827e-194">User1 enters a new message, and then clicks **Send**.</span></span> <span data-ttu-id="6827e-195">常設チャットクライアントは、SIP INFO XCCOS **grpchat** コマンドでチャットルームにメッセージを投稿します。</span><span class="sxs-lookup"><span data-stu-id="6827e-195">The Persistent Chat client posts the message to the chat room in a SIP INFO XCCOS **grpchat** command.</span></span> <span data-ttu-id="6827e-196">常設チャットサーバーは、この新しいメッセージのコピーを常設チャットのバックエンドデータベースに格納します。</span><span class="sxs-lookup"><span data-stu-id="6827e-196">Persistent Chat Server stores a copy of this new message in the Persistent Chat back-end database.</span></span>

5.  <span data-ttu-id="6827e-197">常設チャットサーバーは、既にチャットルームに入っている SIP INFO XCCOS **grpchat** メッセージのコピーを User2 に送信します。</span><span class="sxs-lookup"><span data-stu-id="6827e-197">Persistent Chat Server sends a separate copy of the SIP INFO XCCOS **grpchat** message to User2, who has already entered the chat room.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a><span data-ttu-id="6827e-198">常設チャットコンプライアンスの通話フロー</span><span class="sxs-lookup"><span data-stu-id="6827e-198">Persistent Chat Compliance Call Flows</span></span>

<span data-ttu-id="6827e-199">常設チャットサーバーは、メッセージキュー (MSMQ とも呼ばれます) と、コンプライアンスデータを処理するための追加のコンプライアンスデータベース (メンバー) を使用します。</span><span class="sxs-lookup"><span data-stu-id="6827e-199">Persistent Chat Server uses Message Queuing (also known as MSMQ) and an additional compliance database (mgccomp) to process compliance data.</span></span> <span data-ttu-id="6827e-200">コンプライアンス イベントの処理方法の例として、次のイベントの手順では、メッセージ投稿イベントの処理方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6827e-200">As an example of how compliance events are processed, the following sequence of events describes how a message post event is processed.</span></span>

1.  <span data-ttu-id="6827e-201">ユーザーがメッセージをルームに投稿します。</span><span class="sxs-lookup"><span data-stu-id="6827e-201">A user posts a message to a room.</span></span>

2.  <span data-ttu-id="6827e-202">常設チャットサーバーは、イベントに関する情報をプライベートメッセージキューのキューに格納します。</span><span class="sxs-lookup"><span data-stu-id="6827e-202">Persistent Chat Server places information pertaining to the event in a private Message Queuing queue.</span></span>

3.  <span data-ttu-id="6827e-203">常設チャットコンプライアンスサーバーは、キューからこのイベントを読み取って、後で処理するために、このイベントをこのデータベースに格納します。</span><span class="sxs-lookup"><span data-stu-id="6827e-203">Persistent Chat Compliance server reads this event from the queue, and places it into the mgccomp database for processing later.</span></span>

4.  <span data-ttu-id="6827e-204">永続的なチャットコンプライアンスサーバーは、定期的にデータベース内の一連のイベントを処理し、そのイベントを常設チャットコンプライアンスアダプターに送信して処理します。</span><span class="sxs-lookup"><span data-stu-id="6827e-204">Periodically, the Persistent Chat Compliance server processes a set of events in the database, and sends them to the Persistent Chat Compliance adapter for processing.</span></span>

5.  <span data-ttu-id="6827e-205">アダプターがデータを正常に処理すると、常設チャットのコンプライアンスサーバーは、そのイベントを、このデータベースから削除します。</span><span class="sxs-lookup"><span data-stu-id="6827e-205">If the adapter successfully processes the data, Persistent Chat Compliance server deletes the events from the mgccomp database.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

