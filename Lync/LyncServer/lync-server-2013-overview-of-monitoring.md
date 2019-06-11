---
title: 'Lync Server 2013: 監視の概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of monitoring
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204937(v=OCS.15)
ms:contentKeyID: 48184261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88bfb8170b2334c322c612628daa1f8b9db2473c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-monitoring-in-lync-server-2013"></a><span data-ttu-id="7c119-102">Lync Server 2013 での監視の概要</span><span class="sxs-lookup"><span data-stu-id="7c119-102">Overview of monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c119-103">_**最終更新日:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="7c119-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="7c119-104">Microsoft Lync Server 2013 では、監視を使用して、ユーザーが関与しているコミュニケーションセッションに関する使用状況情報とエクスペリエンス (QoE) データを収集します。</span><span class="sxs-lookup"><span data-stu-id="7c119-104">In Microsoft Lync Server 2013, monitoring is used to collect usage information and Quality of Experience (QoE) data about the communication sessions that your users are involved in.</span></span> <span data-ttu-id="7c119-105">セッションとは、ユーザーの a への接続を表す一般的な用語です。</span><span class="sxs-lookup"><span data-stu-id="7c119-105">A session is a generic term that covers a user’s connection to a:</span></span>

  - <span data-ttu-id="7c119-106">電話会議</span><span class="sxs-lookup"><span data-stu-id="7c119-106">Conference</span></span>

  - <span data-ttu-id="7c119-107">会議のモダリティ (音声/ビデオ、アプリケーション共有など)</span><span class="sxs-lookup"><span data-stu-id="7c119-107">Conferencing modality (such as Audio/Video or Application Sharing)</span></span>

  - <span data-ttu-id="7c119-108">インスタント メッセージングや音声通話などのピアツーピア会話を介した別のユーザー</span><span class="sxs-lookup"><span data-stu-id="7c119-108">Another user via a peer-to-peer conversation such as instant messaging or an audio call</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7c119-109">Lync Server 2013 は、個々のセッションについての情報を追跡します。誰がだれか。セッションで使用されたエンドポイントセッションの最後の所要時間セッションの品質はどのようなものだったのでしょうか。などなど。</span><span class="sxs-lookup"><span data-stu-id="7c119-109">Lync Server 2013 keeps track of information about each session: who called who; which endpoints were used in the session; how long did the session last; what was the perceived quality of the session; and so on.</span></span> <span data-ttu-id="7c119-110">ただし、Lync Server では、実際の通話は記録および保存されません。</span><span class="sxs-lookup"><span data-stu-id="7c119-110">However, Lync Server does not record and store the actual call itself.</span></span> <span data-ttu-id="7c119-111">インスタントメッセージセッションも含まれています。 Lync Server はインスタントメッセージングセッションに関する情報を記録しますが、セッション中に送信されたインスタントメッセージの記録は保持されません。</span><span class="sxs-lookup"><span data-stu-id="7c119-111">That includes instant messaging sessions as well: although Lync Server records information about instant messaging sessions, it does not maintain a record of each instant message that was sent during the session.</span></span>



</div>

<span data-ttu-id="7c119-112">Lync Server によって収集される通話の詳細情報は、次のようなさまざまな用途に使用できます。</span><span class="sxs-lookup"><span data-stu-id="7c119-112">The call detail information collected by Lync Server can be employed for any number of uses, including:</span></span>

  - <span data-ttu-id="7c119-113">**投資収益率 (ROI)**</span><span class="sxs-lookup"><span data-stu-id="7c119-113">**Return on Investment (ROI)**.</span></span> <span data-ttu-id="7c119-114">管理者は、料金を節約し、Lync Server の展開のジャスティフィケーションを行うために、サーバーを監視して、以前のテレフォニーシステムで収集した同様のデータを比較することができます。</span><span class="sxs-lookup"><span data-stu-id="7c119-114">Administrators can compare the usage data collected by Monitoring Server to similar data collected for their previous telephony system in order to show cost savings and help justify the deployment of Lync Server.</span></span>

  - <span data-ttu-id="7c119-115">**デバイス インベントリ管理**。</span><span class="sxs-lookup"><span data-stu-id="7c119-115">**Device Inventory Management**.</span></span> <span data-ttu-id="7c119-116">資産管理情報により、管理者は、置き換える必要がある古いデバイスをまだ使用していることに加えて、まったく使用されていない高価なデバイスを特定することができます。</span><span class="sxs-lookup"><span data-stu-id="7c119-116">Asset management information helps administrators identify old devices still in use that need to be replaced, as well as identify expensive devices that do not appear to be getting used at all.</span></span>

  - <span data-ttu-id="7c119-117">ヘルプデスク</span><span class="sxs-lookup"><span data-stu-id="7c119-117">Help Desk.</span></span> <span data-ttu-id="7c119-118">データのトラブルシューティングを行うと、サポートエンジニアはユーザーの呼び出しが失敗した理由を特定し、サーバーまたはクライアント側のログを収集せずにその操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7c119-118">Troubleshooting data enables support engineers to determine why a user’s call failed, and to do so without having to collect server or client side logs.</span></span> <span data-ttu-id="7c119-119">この情報は、Microsoft Lync 2013 および Lync Server 2013 に関する技術的な知識を持っていないサポート担当者によって、簡単にアクセスして理解することができます。</span><span class="sxs-lookup"><span data-stu-id="7c119-119">This information can be readily accessed and understood by support personnel who do not have a deep technical knowledge of Microsoft Lync 2013 and Lync Server 2013.</span></span>

  - <span data-ttu-id="7c119-p106">**システム トラブルシューティング**。管理者は、エンド ユーザーが会議への参加、通話の確立、インスタント メッセージの送信などの基本的なタスクを実行できなくなるような深刻な問題を検出できます。</span><span class="sxs-lookup"><span data-stu-id="7c119-p106">**System Troubleshooting**. Enables administrators to detect major issues that might prevent end users from performing basic tasks like joining a conference, establishing a call, or sending an instant message.</span></span>

<span data-ttu-id="7c119-122">監視サーバーには、この基本的な通話情報に加えて、SIP エンドポイント (Lync 2013 など) が、他の方法ではアクセスできないトラブルシューティング情報を提供するメカニズムも用意されています。</span><span class="sxs-lookup"><span data-stu-id="7c119-122">In addition to this basic call information, the Monitoring Server also provides a mechanism that allows SIP endpoints (such as Lync 2013) to provide troubleshooting information that the server would not otherwise have access to:</span></span>

  - <span data-ttu-id="7c119-123">**品質に影響するメディア指標**。</span><span class="sxs-lookup"><span data-stu-id="7c119-123">**Media Metrics that Impact Quality**.</span></span> <span data-ttu-id="7c119-124">これらの指標は、通話の実際の伝送を処理します。つまり、ネットワーク上の通話旅として、旅行記録が提供されます。</span><span class="sxs-lookup"><span data-stu-id="7c119-124">These metrics deal with the actual transmission of the call itself; that is, they provide a sort of travel log as the call journeys across the network.</span></span> <span data-ttu-id="7c119-125">これらのメトリック (パケットの損失、ジッター、ラウンドトリップ時間など) には、エンドポイントの停止時点から、他のユーザーのエンドポイントに到着した時点までの通話に何が発生したかが示されます。</span><span class="sxs-lookup"><span data-stu-id="7c119-125">These metrics (which include such things as packet loss, jitter, and round trip times) provide information on what happened to the call from the time it left your endpoint to the time it arrived at the other person's endpoint.</span></span>

  - <span data-ttu-id="7c119-126">**エンド ユーザーにレポートされる問題**。</span><span class="sxs-lookup"><span data-stu-id="7c119-126">**Issues Reported to the End User**.</span></span> <span data-ttu-id="7c119-127">これらのメトリックには、マイクから離れている、音声が小さすぎる、またはネットワーク接続が弱い、またはコンピューター上の別のプログラムが原因で低品質な状態になっている場合に、Lync 2013 によってエンドユーザーに提示される低品質の通知が含まれます。利用可能なリソースを消費します。</span><span class="sxs-lookup"><span data-stu-id="7c119-127">These metrics include poor quality notifications that Lync 2013 presents to end users in cases where they are too far from a microphone, speaking too softly, have a poor network connection, or are experiencing poor quality because another program on the computer is consuming the available resources.</span></span>

  - <span data-ttu-id="7c119-p109">**環境情報**。これらの指標は、使用されているマイクとスピーカーの種類、ユーザーが VPN 接続経由で接続しているかどうか、ユーザーがワイヤレスで接続しているかどうかなど、通話品質要因の詳細を示します。</span><span class="sxs-lookup"><span data-stu-id="7c119-p109">**Environment Information**. These metrics detail call quality factors such as the type of microphone and speakers being used, whether the user is connected through a VPN connection, and whether the user is on a wireless connection.</span></span>

<span data-ttu-id="7c119-130">各通話の終了時に、SIP 準拠のエンドポイントによって、通話を促進するフロントエンドサーバーにこの情報が自動的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="7c119-130">At the end of each call, SIP-compliant endpoints automatically transmit this information to the Front End server that facilitated the call.</span></span> <span data-ttu-id="7c119-131">エンドポイントを取得してその情報を送信するために何もする必要はありません。この動作は SIP プロトコルに組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="7c119-131">You don't have to do anything to get endpoints to transmit that information; that behavior is built into the SIP protocol.</span></span> <span data-ttu-id="7c119-132">ただし、情報を収集して保存する場合は、監視をインストールして有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c119-132">However, if you want to collect and store that information, then you need to install and enable monitoring.</span></span> <span data-ttu-id="7c119-133">監視をインストールして有効にする場合は、フロントエンドサーバー上で実行されているエージェントによって通話情報が収集され、1組の SQL Server データベースに中継されます。</span><span class="sxs-lookup"><span data-stu-id="7c119-133">If you do install and enable monitoring, then call information is gathered by agents running on the Front End server and relayed to a pair of SQL Server databases.</span></span>

<span data-ttu-id="7c119-134">Lync Server 2013 では、監視のインストールと構成のプロセスが簡略化されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7c119-134">Note that the process of installing and configuring monitoring has been simplified in Lync Server 2013.</span></span> <span data-ttu-id="7c119-135">以前のバージョンのソフトウェアでは、監視サーバーの役割を監視する必要があります。通常は、監視サーバーとして使用するために別のコンピューターが別途用意されていました。</span><span class="sxs-lookup"><span data-stu-id="7c119-135">In prior versions of the software, monitoring required a separate Monitoring Server role, which typically meant a separate computer set aside for use as the Monitoring Server.</span></span> <span data-ttu-id="7c119-136">ただし、Lync Server 2013 では、監視サーバーの役割は廃止されました。</span><span class="sxs-lookup"><span data-stu-id="7c119-136">In Lync Server 2013, however, the Monitoring Server role has been eliminated.</span></span> <span data-ttu-id="7c119-137">代わりに、監視サービス ("統合されたデータ収集エージェント" の形式) がすべてのフロントエンドサーバーに併置されています。</span><span class="sxs-lookup"><span data-stu-id="7c119-137">Instead, the monitoring service (in the form of "unified data collection agents") has been collocated into all Front End servers.</span></span> <span data-ttu-id="7c119-138">これには、少なくとも2つの主な利点があります。</span><span class="sxs-lookup"><span data-stu-id="7c119-138">This has at least two major benefits.</span></span> <span data-ttu-id="7c119-139">監視サービスの collocation:</span><span class="sxs-lookup"><span data-stu-id="7c119-139">Collocation of the monitoring service:</span></span>

  - <span data-ttu-id="7c119-140">Lync Server 2013 を実装するときに必要なサーバーの役割の数を減らします。</span><span class="sxs-lookup"><span data-stu-id="7c119-140">Decreases the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="7c119-141">監視サーバーの役割を減らすことは、監視目的で専用のサーバーを維持する必要がないため、コストの削減に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7c119-141">Decrementing the Monitoring Server role also helps reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="7c119-142">Lync Server 2013 のセットアップと管理の複雑さを軽減します。</span><span class="sxs-lookup"><span data-stu-id="7c119-142">Reduces the complexity of Lync Server 2013 setup and administration.</span></span> <span data-ttu-id="7c119-143">各フロントエンドサーバーで監視サービスを特定することで、監視サーバーの役割をインストール、構成、および管理する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="7c119-143">By collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<span data-ttu-id="7c119-144">詳細については、「Lync Server 2013 2013 展開ガイド」の「 [Lync server 2013 での監視の展開](lync-server-2013-deploying-monitoring.md)に関するトピック」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c119-144">For more information see the topic [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md) in the Lync Server 2013 2013 deployment guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

