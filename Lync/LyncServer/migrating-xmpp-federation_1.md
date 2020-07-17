---
title: XMPP フェデレーションの移行
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e446a4981a3b9b255311ff5720e2c6dc36d61e9a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a><span data-ttu-id="8cdba-102">XMPP フェデレーションの移行</span><span class="sxs-lookup"><span data-stu-id="8cdba-102">Migrating XMPP federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cdba-103">_**トピックの最終更新日:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="8cdba-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="8cdba-104">以前のバージョンの Office Communications Server では、拡張可能なメッセージングとプレゼンスプロトコル (XMPP) ゲートウェイが提供されていました。これは、別のサーバーの役割として展開して、XMPP の展開とのフェデレーションを可能にします。</span><span class="sxs-lookup"><span data-stu-id="8cdba-104">Previous versions of Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="8cdba-105">Lync Server 2013 では、XMPP 機能を機能として展開できます。</span><span class="sxs-lookup"><span data-stu-id="8cdba-105">In Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="8cdba-106">XMPP 機能は、Lync server 2013 エッジサーバー上で実行される XMPP プロキシとして、または Lync Server 2013 フロントエンドサーバー上で実行される XMPP ゲートウェイとして、次の2つの部分に分けてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8cdba-106">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the Lync Server 2013 Edge Server, and the XMPP Gateway that runs on the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="8cdba-107">移行の観点から、Office Communications Server 2007 R2 ユーザーアカウントを Lync Server 2013 プールに移動して、Office Communications Server 2007 R2 XMPP ゲートウェイを引き続き使用することができます。</span><span class="sxs-lookup"><span data-stu-id="8cdba-107">From a migration perspective, a Office Communications Server 2007 R2 user account can be moved to a Lync Server 2013 pool and continue to use the Office Communications Server 2007 R2 XMPP gateway.</span></span> <span data-ttu-id="8cdba-108">これは、Lync Server 2013 で XMPP フェデレーションパートナーが構成されていない場合にのみ可能です。</span><span class="sxs-lookup"><span data-stu-id="8cdba-108">This is possible only when the XMPP federated partner is not configured in Lync Server 2013.</span></span>

<span data-ttu-id="8cdba-109">要約すると、office communications server が 2007 R2 XMPP ゲートウェイと共に展開されていて、従来の Office Communications Server 2007 R2 ユーザーに対して XMPP フェデレーションが有効になっている場合、XMPP フェデレーションを Lync Server 2013 に移行するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="8cdba-109">In summary, if Office Communications Server has been deployed with the Office Communications Server 2007 R2 XMPP Gateway and XMPP federation has been enabled for legacy Office Communications Server 2007 R2 users, to migrate the XMPP federation to Lync Server 2013:</span></span>

1.  <span data-ttu-id="8cdba-110">Lync Server 2013 プールを展開します。</span><span class="sxs-lookup"><span data-stu-id="8cdba-110">Deploy a Lync Server 2013 pool.</span></span>

2.  <span data-ttu-id="8cdba-111">Lync Server 2013 エッジサーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="8cdba-111">Deploy a Lync Server 2013 Edge server.</span></span>

3.  <span data-ttu-id="8cdba-112">すべてのユーザーを Lync Server 2013 プールに移動します。</span><span class="sxs-lookup"><span data-stu-id="8cdba-112">Move all users to the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="8cdba-113">エッジ サーバーの XMPP アクセス ポリシーと証明書を作成します。</span><span class="sxs-lookup"><span data-stu-id="8cdba-113">Create XMPP access policies and certificates for the Edge Server.</span></span>

5.  <span data-ttu-id="8cdba-114">Lync Server 2013 で XMPP フェデレーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8cdba-114">Enable XMPP federation in Lync Server 2013.</span></span> 

6.  <span data-ttu-id="8cdba-115">Lync Server 2013 XMPP ゲートウェイをポイントするように DNS エントリを更新します。</span><span class="sxs-lookup"><span data-stu-id="8cdba-115">Update the DNS entries to point to the Lync Server 2013 XMPP Gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

