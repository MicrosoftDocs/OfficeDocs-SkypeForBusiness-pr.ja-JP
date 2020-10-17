---
title: 'Lync Server 2013: 監視の概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of monitoring
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204937(v=OCS.15)
ms:contentKeyID: 48184261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c44ef02ef0685b4f930d7a264915d5338600ef71
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520844"
---
# <a name="overview-of-monitoring-in-lync-server-2013"></a><span data-ttu-id="19642-102">Lync Server 2013 での監視の概要</span><span class="sxs-lookup"><span data-stu-id="19642-102">Overview of monitoring in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19642-103">_**トピックの最終更新日:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="19642-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="19642-104">Microsoft Lync Server 2013 では、監視を使用して、ユーザーが関与する通信セッションに関する使用状況の情報と QoE (Quality of Experience) データを収集します。</span><span class="sxs-lookup"><span data-stu-id="19642-104">In Microsoft Lync Server 2013, monitoring is used to collect usage information and Quality of Experience (QoE) data about the communication sessions that your users are involved in.</span></span> <span data-ttu-id="19642-105">セッションとは、次のものへのユーザーの接続に適用される汎用的な用語です。</span><span class="sxs-lookup"><span data-stu-id="19642-105">A session is a generic term that covers a user’s connection to a:</span></span>

  - <span data-ttu-id="19642-106">会議</span><span class="sxs-lookup"><span data-stu-id="19642-106">Conference</span></span>

  - <span data-ttu-id="19642-107">会議モダリティ (音声ビデオやアプリケーション共有など)</span><span class="sxs-lookup"><span data-stu-id="19642-107">Conferencing modality (such as Audio/Video or Application Sharing)</span></span>

  - <span data-ttu-id="19642-108">インスタント メッセージングや音声通話などのピアツーピア会話を介した別のユーザー</span><span class="sxs-lookup"><span data-stu-id="19642-108">Another user via a peer-to-peer conversation such as instant messaging or an audio call</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="19642-109">Lync Server 2013 は、各セッションについての情報を追跡します。誰がだれを呼び出したか。セッションで使用されたエンドポイント。セッションの最後の時間。セッションの認識された品質。などなど。</span><span class="sxs-lookup"><span data-stu-id="19642-109">Lync Server 2013 keeps track of information about each session: who called who; which endpoints were used in the session; how long did the session last; what was the perceived quality of the session; and so on.</span></span> <span data-ttu-id="19642-110">ただし、Lync Server は、実際の通話自体を記録して保存することはありません。</span><span class="sxs-lookup"><span data-stu-id="19642-110">However, Lync Server does not record and store the actual call itself.</span></span> <span data-ttu-id="19642-111">これには、インスタントメッセージングセッションも含まれています。 Lync Server はインスタントメッセージングセッションに関する情報を記録しますが、セッション中に送信されたインスタントメッセージのレコードは保持されません。</span><span class="sxs-lookup"><span data-stu-id="19642-111">That includes instant messaging sessions as well: although Lync Server records information about instant messaging sessions, it does not maintain a record of each instant message that was sent during the session.</span></span>



</div>

<span data-ttu-id="19642-112">Lync Server で収集された通話詳細情報は、次のような任意の数の用途に使用できます。</span><span class="sxs-lookup"><span data-stu-id="19642-112">The call detail information collected by Lync Server can be employed for any number of uses, including:</span></span>

  - <span data-ttu-id="19642-113">**投資収益率 (ROI)**。</span><span class="sxs-lookup"><span data-stu-id="19642-113">**Return on Investment (ROI)**.</span></span> <span data-ttu-id="19642-114">管理者は、監視サーバーによって収集された利用状況データを、以前のテレフォニーシステムで収集された類似データに比較して、費用の節約を示し、Lync Server の展開を正当化することができます。</span><span class="sxs-lookup"><span data-stu-id="19642-114">Administrators can compare the usage data collected by Monitoring Server to similar data collected for their previous telephony system in order to show cost savings and help justify the deployment of Lync Server.</span></span>

  - <span data-ttu-id="19642-p104">**デバイス インベントリ管理**。資産管理情報により、管理者は、交換が必要だがまだ使用されている古いデバイスと、まったく使用されていないように見える高価なデバイスを識別できます。</span><span class="sxs-lookup"><span data-stu-id="19642-p104">**Device Inventory Management**. Asset management information helps administrators identify old devices still in use that need to be replaced, as well as identify expensive devices that do not appear to be getting used at all.</span></span>

  - <span data-ttu-id="19642-117">ヘルプ デスク。</span><span class="sxs-lookup"><span data-stu-id="19642-117">Help Desk.</span></span> <span data-ttu-id="19642-118">データのトラブルシューティングを行うと、サポートエンジニアは、サーバーまたはクライアント側のログを収集せずに、ユーザーの呼び出しが失敗した理由を特定し、それを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="19642-118">Troubleshooting data enables support engineers to determine why a user’s call failed, and to do so without having to collect server or client side logs.</span></span> <span data-ttu-id="19642-119">この情報は、Microsoft Lync 2013 および Lync Server 2013 に関する詳細な技術的知識を持たないサポート担当者が、すぐにアクセスして理解することができます。</span><span class="sxs-lookup"><span data-stu-id="19642-119">This information can be readily accessed and understood by support personnel who do not have a deep technical knowledge of Microsoft Lync 2013 and Lync Server 2013.</span></span>

  - <span data-ttu-id="19642-p106">**システム トラブルシューティング**。管理者は、エンド ユーザーが会議への参加、通話の確立、インスタント メッセージの送信などの基本的なタスクを実行できなくなる主な問題を検出できます。</span><span class="sxs-lookup"><span data-stu-id="19642-p106">**System Troubleshooting**. Enables administrators to detect major issues that might prevent end users from performing basic tasks like joining a conference, establishing a call, or sending an instant message.</span></span>

<span data-ttu-id="19642-122">この基本的な呼び出し情報に加えて、監視サーバーは、SIP エンドポイント (Lync 2013 など) が、それ以外の方法でアクセスできないトラブルシューティング情報を提供するメカニズムも提供します。</span><span class="sxs-lookup"><span data-stu-id="19642-122">In addition to this basic call information, the Monitoring Server also provides a mechanism that allows SIP endpoints (such as Lync 2013) to provide troubleshooting information that the server would not otherwise have access to:</span></span>

  - <span data-ttu-id="19642-p107">**品質に影響するメディア指標**。これらの指標は、通話の実際の送信を処理します。つまり、ネットワーク上の通話の経路として一種のトラベル ログを提供します。これらの指標 (パケット損失、ジッター、往復時間などを含む) は、通話がエンドポイントで発信されてから他のユーザーのエンドポイントに到達するまでに起きたことに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="19642-p107">**Media Metrics that Impact Quality**. These metrics deal with the actual transmission of the call itself; that is, they provide a sort of travel log as the call journeys across the network. These metrics (which include such things as packet loss, jitter, and round trip times) provide information on what happened to the call from the time it left your endpoint to the time it arrived at the other person's endpoint.</span></span>

  - <span data-ttu-id="19642-126">**エンド ユーザーにレポートされる問題**。</span><span class="sxs-lookup"><span data-stu-id="19642-126">**Issues Reported to the End User**.</span></span> <span data-ttu-id="19642-127">これらの指標には、コンピューター上の他のプログラムが利用可能なリソースを消費しているために、マイクから遠すぎる、または音声が小さすぎる、またはネットワーク接続が不足している、または品質が低下しているなど、Lync 2013 がエンドユーザーに対して表示される低品質の通知が含まれます。</span><span class="sxs-lookup"><span data-stu-id="19642-127">These metrics include poor quality notifications that Lync 2013 presents to end users in cases where they are too far from a microphone, speaking too softly, have a poor network connection, or are experiencing poor quality because another program on the computer is consuming the available resources.</span></span>

  - <span data-ttu-id="19642-p109">**環境情報**。これらの指標は、使用されているマイクとスピーカーの種類、ユーザーが VPN 接続経由で接続しているかどうか、ユーザーがワイヤレスで接続しているかどうかなど、通話品質要因の詳細を示します。</span><span class="sxs-lookup"><span data-stu-id="19642-p109">**Environment Information**. These metrics detail call quality factors such as the type of microphone and speakers being used, whether the user is connected through a VPN connection, and whether the user is on a wireless connection.</span></span>

<span data-ttu-id="19642-p110">各通話の終了時に、SIP 対応のエンドポイントは通話を促進したフロントエンド サーバーにこの情報を自動的に送信します。その情報を送信するためにエンドポイントで何も実行する必要はありません。この動作は SIP プロトコルに組み込まれています。ただし、その情報を収集して保存する場合は、監視をインストールして有効にする必要があります。監視をインストールして有効にした場合、通話情報はフロントエンド サーバーで実行されているエージェントによって収集され、SQL Server データベースのペアに中継されます。</span><span class="sxs-lookup"><span data-stu-id="19642-p110">At the end of each call, SIP-compliant endpoints automatically transmit this information to the Front End server that facilitated the call. You don't have to do anything to get endpoints to transmit that information; that behavior is built into the SIP protocol. However, if you want to collect and store that information, then you need to install and enable monitoring. If you do install and enable monitoring, then call information is gathered by agents running on the Front End server and relayed to a pair of SQL Server databases.</span></span>

<span data-ttu-id="19642-134">Lync Server 2013 では、監視のインストールと構成のプロセスが簡略化されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="19642-134">Note that the process of installing and configuring monitoring has been simplified in Lync Server 2013.</span></span> <span data-ttu-id="19642-135">以前のバージョンのソフトウェアでは、監視に別の監視サーバーの役割が必要であり、これは通常監視サーバーとして使用する別のコンピューターを意味しました。</span><span class="sxs-lookup"><span data-stu-id="19642-135">In prior versions of the software, monitoring required a separate Monitoring Server role, which typically meant a separate computer set aside for use as the Monitoring Server.</span></span> <span data-ttu-id="19642-136">ただし、Lync Server 2013 では、監視サーバーの役割は廃止されました。</span><span class="sxs-lookup"><span data-stu-id="19642-136">In Lync Server 2013, however, the Monitoring Server role has been eliminated.</span></span> <span data-ttu-id="19642-137">代わりに、監視サービス ("統合データ収集エージェント" の形式) がフロントエンド サーバーに配置されました。</span><span class="sxs-lookup"><span data-stu-id="19642-137">Instead, the monitoring service (in the form of "unified data collection agents") has been collocated into all Front End servers.</span></span> <span data-ttu-id="19642-138">これには少なくとも 2 つの大きな利点があります。</span><span class="sxs-lookup"><span data-stu-id="19642-138">This has at least two major benefits.</span></span> <span data-ttu-id="19642-139">監視サービスの配置には次の利点があります。</span><span class="sxs-lookup"><span data-stu-id="19642-139">Collocation of the monitoring service:</span></span>

  - <span data-ttu-id="19642-140">Lync Server 2013 を実装するときに必要なサーバーの役割の数を減らします。</span><span class="sxs-lookup"><span data-stu-id="19642-140">Decreases the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="19642-141">監視サーバーの役割の数が減ると、監視用に専用サーバーを管理する必要がなくなるため、コストも削減されます。</span><span class="sxs-lookup"><span data-stu-id="19642-141">Decrementing the Monitoring Server role also helps reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="19642-142">Lync Server 2013 のセットアップと管理の複雑さが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="19642-142">Reduces the complexity of Lync Server 2013 setup and administration.</span></span> <span data-ttu-id="19642-143">監視サービスを各フロントエンド サーバーに配置することで、監視サーバーの役割をインストール、構成、および管理する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="19642-143">By collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<span data-ttu-id="19642-144">詳細については、「Lync Server 2013 2013 展開ガイド」の「 [Lync server 2013 での監視の展開](lync-server-2013-deploying-monitoring.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19642-144">For more information see the topic [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md) in the Lync Server 2013 2013 deployment guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

