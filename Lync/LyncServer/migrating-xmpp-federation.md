---
title: XMPP フェデレーションの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49733794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dbfc5da555ddf81f7ae542a552c503cc2c24272
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148806"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a><span data-ttu-id="af8e0-102">XMPP フェデレーションの移行</span><span class="sxs-lookup"><span data-stu-id="af8e0-102">Migrating XMPP federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af8e0-103">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="af8e0-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="af8e0-104">以前のバージョンの Lync Server および Office Communications Server では、XMPP 展開とのフェデレーションを可能にするために、個別のサーバーの役割として展開できる拡張メッセージングおよびプレゼンスプロトコル (XMPP) ゲートウェイが提供されていました。</span><span class="sxs-lookup"><span data-stu-id="af8e0-104">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="af8e0-105">Lync Server 2013 では、XMPP 機能を機能として展開できます。</span><span class="sxs-lookup"><span data-stu-id="af8e0-105">In Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="af8e0-106">XMPP 機能は、Lync server 2013 エッジサーバー上で実行される XMPP プロキシとして、または Lync Server 2013 フロントエンドサーバー上で実行される XMPP ゲートウェイとして、次の2つの部分に分けてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="af8e0-106">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the Lync Server 2013 Edge Server, and the XMPP Gateway that runs on the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="af8e0-107">移行の観点から、Lync Server ユーザーアカウントを Lync Server 2013 プールに移動し、従来の XMPP ゲートウェイを引き続き使用することができます。</span><span class="sxs-lookup"><span data-stu-id="af8e0-107">From a migration perspective, a Lync Server user account can be moved to a Lync Server 2013 pool and continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="af8e0-108">これは、Lync Server 2013 で XMPP フェデレーションパートナーが構成されていない場合にのみ可能です。</span><span class="sxs-lookup"><span data-stu-id="af8e0-108">This is possible only when the XMPP federated partner is not configured in Lync Server 2013.</span></span>

<span data-ttu-id="af8e0-109">要約すると、Lync Server 2010 が Office Communications Server 2007 R2 XMPP ゲートウェイを使用して展開されており、レガシ Lync Server 2010 ユーザーに対して XMPP フェデレーションが有効になっている場合、XMPP フェデレーションを Lync Server 2013 に移行するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="af8e0-109">In summary, if Lync Server 2010 has been deployed with the Office Communications Server 2007 R2 XMPP Gateway and XMPP federation has been enabled for legacy Lync Server 2010 users, to migrate the XMPP federation to Lync Server 2013:</span></span>

1.  <span data-ttu-id="af8e0-110">Lync Server 2013 プールを展開します。</span><span class="sxs-lookup"><span data-stu-id="af8e0-110">Deploy a Lync Server 2013 pool.</span></span>

2.  <span data-ttu-id="af8e0-111">Lync Server 2013 エッジサーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="af8e0-111">Deploy a Lync Server 2013 Edge server.</span></span>

3.  <span data-ttu-id="af8e0-112">すべてのユーザーを Lync Server 2013 プールに移動する</span><span class="sxs-lookup"><span data-stu-id="af8e0-112">Move all users to the Lync Server 2013 pool</span></span>

4.  <span data-ttu-id="af8e0-113">エッジ サーバーの XMPP アクセス ポリシーと証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="af8e0-113">Create XMPP access policies and certificates for the Edge Server.</span></span>

5.  <span data-ttu-id="af8e0-114">Lync Server 2013 で XMPP フェデレーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="af8e0-114">Enable XMPP federation in Lync Server 2013.</span></span> 

6.  <span data-ttu-id="af8e0-115">Lync Server 2013 XMPP ゲートウェイをポイントするように DNS エントリを更新します。</span><span class="sxs-lookup"><span data-stu-id="af8e0-115">Update the DNS entries to point to the Lync Server 2013 XMPP Gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

