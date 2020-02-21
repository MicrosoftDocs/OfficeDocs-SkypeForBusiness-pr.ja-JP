---
title: 'Lync Server 2013: 仲介サーバーの展開とピアの定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Mediation Servers and defining peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48185077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03eca427f644d6f94ae7a52900b80320e2517ed2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a><span data-ttu-id="277f8-102">Lync Server 2013 での仲介サーバーの展開とピアの定義</span><span class="sxs-lookup"><span data-stu-id="277f8-102">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="277f8-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="277f8-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="277f8-104">エンタープライズ Voip ワークロード、ダイヤルイン会議、および高度なエンタープライズ Voip アプリケーション (応答グループアプリケーション、コールパークアプリケーション、通話受付管理 (CAC) など) は、フロントエンドプールで利用できます。</span><span class="sxs-lookup"><span data-stu-id="277f8-104">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="277f8-105">Lync Server 2013 では、仲介サーバーの機能はフロントエンドサーバーに組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="277f8-105">With Lync Server 2013, the functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="277f8-106">独立したスタンドアロンの仲介サーバーは不要になりました。</span><span class="sxs-lookup"><span data-stu-id="277f8-106">A separate stand-alone Mediation Server is no longer necessary.</span></span> <span data-ttu-id="277f8-107">フロントエンドプールは、サポートされているゲートウェイ (公衆交換電話網 (PSTN) ゲートウェイまたは ip-pbx) と直接通信することができ、仲介サーバーが仲介者として機能する必要性を排除します。</span><span class="sxs-lookup"><span data-stu-id="277f8-107">Front End pools can communicate directly with supported gateways (a public switched telephone network (PSTN) gateway or an IP-PBX), removing the need for a Mediation Server to serve as an intermediary.</span></span>

<span data-ttu-id="277f8-108">唯一の例外は、インターネット テレフォニー サービス プロバイダーのセッション ボーダー コントローラーに接続する SIP トランクを構成する場合です。</span><span class="sxs-lookup"><span data-stu-id="277f8-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="277f8-109">エンタープライズ Voip インフラストラクチャを SIP トランクプロバイダーに接続するには、個別の仲介サーバーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="277f8-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>

<span data-ttu-id="277f8-110">Lync Server (フロントエンドプールまたはスタンドアロン仲介サーバー上の仲介サーバーコンポーネント) とゲートウェイとの間の接続は、*トランク*と呼ばれる論理的な関連付けとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="277f8-110">The connection between Lync Server (the Mediation Server component on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a *trunk*.</span></span> <span data-ttu-id="277f8-111">このセクションのトピックでは、トランクを定義する方法と、SIP トランクに接続する場合にスタンドアロンの仲介サーバーを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="277f8-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="277f8-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="277f8-112">In This Section</span></span>

  - [<span data-ttu-id="277f8-113">Lync Server 2013 のトポロジビルダーでの仲介サーバーの定義</span><span class="sxs-lookup"><span data-stu-id="277f8-113">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [<span data-ttu-id="277f8-114">Lync Server 2013 のトポロジビルダーでゲートウェイを定義する</span><span class="sxs-lookup"><span data-stu-id="277f8-114">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [<span data-ttu-id="277f8-115">Lync Server 2013 での仲介サーバーのファイルのインストール</span><span class="sxs-lookup"><span data-stu-id="277f8-115">Install the files for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-install-the-files-for-mediation-server.md)

  - [<span data-ttu-id="277f8-116">Lync Server 2013 のトポロジビルダーでの追加トランクの定義</span><span class="sxs-lookup"><span data-stu-id="277f8-116">Define additional trunks in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="277f8-117">関連情報</span><span class="sxs-lookup"><span data-stu-id="277f8-117">Related Sections</span></span>

[<span data-ttu-id="277f8-118">Lync Server 2013 でのダイヤルイン会議の構成</span><span class="sxs-lookup"><span data-stu-id="277f8-118">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

