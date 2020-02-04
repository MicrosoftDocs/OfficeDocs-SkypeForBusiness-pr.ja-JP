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
ms.openlocfilehash: 3b72dabd60ea42a84fcf9b15d1d739bc063ddf1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762875"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a><span data-ttu-id="aaea2-102">XMPP フェデレーションの移行</span><span class="sxs-lookup"><span data-stu-id="aaea2-102">Migrating XMPP federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aaea2-103">_**最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="aaea2-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="aaea2-104">以前のバージョンの Lync Server と Office Communications Server では、拡張されたメッセージング機能とプレゼンスプロトコル (XMPP) ゲートウェイが提供されており、これを個別のサーバーの役割として展開して、XMPP の展開とのフェデレーションを可能にすることができました。</span><span class="sxs-lookup"><span data-stu-id="aaea2-104">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="aaea2-105">Lync Server 2013 では、機能として XMPP 機能を展開できます。</span><span class="sxs-lookup"><span data-stu-id="aaea2-105">In Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="aaea2-106">XMPP 機能は、Lync Server 2013 エッジサーバー上で実行される XMPP プロキシとして、または Lync Server 2013 フロントエンドサーバー上で実行される XMPP ゲートウェイとして、2つの部分でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="aaea2-106">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the Lync Server 2013 Edge Server, and the XMPP Gateway that runs on the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="aaea2-107">移行の観点から、Lync Server のユーザーアカウントを Lync Server 2013 プールに移動して、従来の XMPP ゲートウェイを引き続き使用することができます。</span><span class="sxs-lookup"><span data-stu-id="aaea2-107">From a migration perspective, a Lync Server user account can be moved to a Lync Server 2013 pool and continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="aaea2-108">これは、Lync Server 2013 で XMPP フェデレーションパートナーが構成されていない場合にのみ可能です。</span><span class="sxs-lookup"><span data-stu-id="aaea2-108">This is possible only when the XMPP federated partner is not configured in Lync Server 2013.</span></span>

<span data-ttu-id="aaea2-109">概要では、Lync Server 2010 が Office Communications Server 2007 R2 XMPP ゲートウェイで展開され、従来の Lync Server 2010 ユーザーに対して XMPP フェデレーションが有効になっている場合、XMPP フェデレーションを Lync Server 2013 に移行します。</span><span class="sxs-lookup"><span data-stu-id="aaea2-109">In summary, if Lync Server 2010 has been deployed with the Office Communications Server 2007 R2 XMPP Gateway and XMPP federation has been enabled for legacy Lync Server 2010 users, to migrate the XMPP federation to Lync Server 2013:</span></span>

1.  <span data-ttu-id="aaea2-110">Lync Server 2013 プールを展開します。</span><span class="sxs-lookup"><span data-stu-id="aaea2-110">Deploy a Lync Server 2013 pool.</span></span>

2.  <span data-ttu-id="aaea2-111">Lync Server 2013 エッジサーバーを展開する。</span><span class="sxs-lookup"><span data-stu-id="aaea2-111">Deploy a Lync Server 2013 Edge server.</span></span>

3.  <span data-ttu-id="aaea2-112">すべてのユーザーを Lync Server 2013 プールに移動する</span><span class="sxs-lookup"><span data-stu-id="aaea2-112">Move all users to the Lync Server 2013 pool</span></span>

4.  <span data-ttu-id="aaea2-113">エッジサーバー用の XMPP アクセスポリシーと証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="aaea2-113">Create XMPP access policies and certificates for the Edge Server.</span></span>

5.  <span data-ttu-id="aaea2-114">Lync Server 2013 で XMPP フェデレーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="aaea2-114">Enable XMPP federation in Lync Server 2013.</span></span> 

6.  <span data-ttu-id="aaea2-115">Lync Server 2013 XMPP ゲートウェイをポイントするように DNS エントリを更新します。</span><span class="sxs-lookup"><span data-stu-id="aaea2-115">Update the DNS entries to point to the Lync Server 2013 XMPP Gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

