---
title: 'Lync Server 2013: 仲介サーバーの展開とピアの定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Mediation Servers and defining peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48185077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b01ccf2e3822933842249df012877b13d10baef3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a><span data-ttu-id="8acaa-102">Lync Server 2013 での仲介サーバーの展開とピアの定義</span><span class="sxs-lookup"><span data-stu-id="8acaa-102">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8acaa-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="8acaa-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="8acaa-104">エンタープライズボイスワークロード、ダイヤルイン会議、高度なエンタープライズボイスアプリケーション (応答グループアプリケーション、コールパークアプリケーション、通話受付制御 (CAC) など) は、フロントエンドプールで利用できます。</span><span class="sxs-lookup"><span data-stu-id="8acaa-104">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="8acaa-105">Lync Server 2013 では、仲介サーバーの機能がフロントエンドサーバーに組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="8acaa-105">With Lync Server 2013, the functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="8acaa-106">独立したスタンドアロンの仲介サーバーは必要なくなりました。</span><span class="sxs-lookup"><span data-stu-id="8acaa-106">A separate stand-alone Mediation Server is no longer necessary.</span></span> <span data-ttu-id="8acaa-107">フロントエンドプールは、サポートされているゲートウェイ (公衆交換電話網 (PSTN) ゲートウェイまたは IP PBX) と直接通信することができ、仲介サーバーが介在して機能する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="8acaa-107">Front End pools can communicate directly with supported gateways (a public switched telephone network (PSTN) gateway or an IP-PBX), removing the need for a Mediation Server to serve as an intermediary.</span></span>

<span data-ttu-id="8acaa-108">唯一の例外は、インターネット テレフォニー サービス プロバイダーのセッション ボーダー コントローラーに接続する SIP トランクを構成する場合です。</span><span class="sxs-lookup"><span data-stu-id="8acaa-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="8acaa-109">エンタープライズ Voip インフラストラクチャを SIP トランクプロバイダに接続するには、個別の仲介サーバーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8acaa-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>

<span data-ttu-id="8acaa-110">Lync Server (フロントエンドプールまたはスタンドアロンの仲介サーバー上の仲介サーバーコンポーネント) とゲートウェイの間の接続は、*トランク*と呼ばれる論理的な関連付けとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="8acaa-110">The connection between Lync Server (the Mediation Server component on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a *trunk*.</span></span> <span data-ttu-id="8acaa-111">このセクションのトピックでは、SIP トランクに接続している場合に、トランクを定義し、スタンドアロンの仲介サーバーを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8acaa-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8acaa-112">このセクション中</span><span class="sxs-lookup"><span data-stu-id="8acaa-112">In This Section</span></span>

  - [<span data-ttu-id="8acaa-113">Lync Server 2013 でのトポロジビルダーでの仲介サーバーの定義</span><span class="sxs-lookup"><span data-stu-id="8acaa-113">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [<span data-ttu-id="8acaa-114">Lync Server 2013 でのトポロジビルダーでのゲートウェイの定義</span><span class="sxs-lookup"><span data-stu-id="8acaa-114">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [<span data-ttu-id="8acaa-115">Lync Server 2013 で仲介サーバー用のファイルをインストールする</span><span class="sxs-lookup"><span data-stu-id="8acaa-115">Install the files for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-install-the-files-for-mediation-server.md)

  - [<span data-ttu-id="8acaa-116">Lync Server 2013 のトポロジビルダーで追加の trunks を定義する</span><span class="sxs-lookup"><span data-stu-id="8acaa-116">Define additional trunks in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="8acaa-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="8acaa-117">Related Sections</span></span>

[<span data-ttu-id="8acaa-118">Lync Server 2013 でのダイヤルイン会議の構成</span><span class="sxs-lookup"><span data-stu-id="8acaa-118">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

