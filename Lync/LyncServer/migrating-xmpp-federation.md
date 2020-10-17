---
title: XMPP フェデレーションの移行
description: XMPP フェデレーションを移行する。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49733794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e63c9f6fd3f1c1d45de77c27417987505678f74b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543213"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="50a7e-103">XMPP フェデレーションの移行</span><span class="sxs-lookup"><span data-stu-id="50a7e-103">Migrating XMPP federation</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50a7e-104">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="50a7e-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="50a7e-105">以前のバージョンの Lync Server および Office Communications Server では、XMPP 展開とのフェデレーションを可能にするために、個別のサーバーの役割として展開できる拡張メッセージングおよびプレゼンスプロトコル (XMPP) ゲートウェイが提供されていました。</span><span class="sxs-lookup"><span data-stu-id="50a7e-105">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="50a7e-106">Lync Server 2013 では、XMPP 機能を機能として展開できます。</span><span class="sxs-lookup"><span data-stu-id="50a7e-106">In Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="50a7e-107">XMPP 機能は、Lync server 2013 エッジサーバー上で実行される XMPP プロキシとして、または Lync Server 2013 フロントエンドサーバー上で実行される XMPP ゲートウェイとして、次の2つの部分に分けてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="50a7e-107">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the Lync Server 2013 Edge Server, and the XMPP Gateway that runs on the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="50a7e-108">移行の観点から、Lync Server ユーザーアカウントを Lync Server 2013 プールに移動し、従来の XMPP ゲートウェイを引き続き使用することができます。</span><span class="sxs-lookup"><span data-stu-id="50a7e-108">From a migration perspective, a Lync Server user account can be moved to a Lync Server 2013 pool and continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="50a7e-109">これは、Lync Server 2013 で XMPP フェデレーションパートナーが構成されていない場合にのみ可能です。</span><span class="sxs-lookup"><span data-stu-id="50a7e-109">This is possible only when the XMPP federated partner is not configured in Lync Server 2013.</span></span>

<span data-ttu-id="50a7e-110">要約すると、Lync Server 2010 が Office Communications Server 2007 R2 XMPP ゲートウェイを使用して展開されており、レガシ Lync Server 2010 ユーザーに対して XMPP フェデレーションが有効になっている場合、XMPP フェデレーションを Lync Server 2013 に移行するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="50a7e-110">In summary, if Lync Server 2010 has been deployed with the Office Communications Server 2007 R2 XMPP Gateway and XMPP federation has been enabled for legacy Lync Server 2010 users, to migrate the XMPP federation to Lync Server 2013:</span></span>

1.  <span data-ttu-id="50a7e-111">Lync Server 2013 プールを展開します。</span><span class="sxs-lookup"><span data-stu-id="50a7e-111">Deploy a Lync Server 2013 pool.</span></span>

2.  <span data-ttu-id="50a7e-112">Lync Server 2013 エッジサーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="50a7e-112">Deploy a Lync Server 2013 Edge server.</span></span>

3.  <span data-ttu-id="50a7e-113">すべてのユーザーを Lync Server 2013 プールに移動する</span><span class="sxs-lookup"><span data-stu-id="50a7e-113">Move all users to the Lync Server 2013 pool</span></span>

4.  <span data-ttu-id="50a7e-114">エッジ サーバーの XMPP アクセス ポリシーと証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="50a7e-114">Create XMPP access policies and certificates for the Edge Server.</span></span>

5.  <span data-ttu-id="50a7e-115">Lync Server 2013 で XMPP フェデレーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="50a7e-115">Enable XMPP federation in Lync Server 2013.</span></span> 

6.  <span data-ttu-id="50a7e-116">Lync Server 2013 XMPP ゲートウェイをポイントするように DNS エントリを更新します。</span><span class="sxs-lookup"><span data-stu-id="50a7e-116">Update the DNS entries to point to the Lync Server 2013 XMPP Gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

