---
title: 常設チャットサーバーの下位互換性を実行する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 329415e7bae43bbbfd3a77da39e99049f4fe617e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-backward-compatibility-for-persistent-chat-server"></a><span data-ttu-id="837fd-102">常設チャットサーバーの下位互換性を実行する</span><span class="sxs-lookup"><span data-stu-id="837fd-102">Run backward compatibility for Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="837fd-103">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="837fd-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="837fd-104">Lync Server 2013、常設チャットサーバーエンドポイントは、常設チャットサーバープールを指す簡単な URL を作成する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="837fd-104">The Lync Server 2013, Persistent Chat Server endpoint provides a way to create a simple URL that points to a Persistent Chat Server pool.</span></span> <span data-ttu-id="837fd-105">これはレガシクライアント (Microsoft Office Communications Server 2007 R2 グループチャットサーバーまたは Lync Server 2010、グループチャット) の場合に便利です。これは、ユーザーがレガシクライアントを Lync 2013 を実行しているコンピューターに接続しようとしているときに、手動構成で簡単な URL を入力できるためです。常設チャット。</span><span class="sxs-lookup"><span data-stu-id="837fd-105">This is useful for legacy clients (Microsoft Office Communications Server 2007 R2 Group Chat Server or Lync Server 2010, Group Chat) because users can enter a simple URL in the manual configuration when trying to point the legacy client to a computer running Lync 2013, Persistent Chat.</span></span> <span data-ttu-id="837fd-106">このエンドポイントは常設チャットでは使用されていません。レガシークライアントにのみ必要になります。</span><span class="sxs-lookup"><span data-stu-id="837fd-106">This endpoint isn’t used by Persistent Chat, and is required for legacy clients only.</span></span> <span data-ttu-id="837fd-107">これは、会議室が移行される中間期間では便利ですが、Lync 2013 クライアントは組織全体に展開されていません。</span><span class="sxs-lookup"><span data-stu-id="837fd-107">This is useful for the interim period where rooms may be migrated, but the Lync 2013 clients have not been deployed throughout the organization.</span></span> <span data-ttu-id="837fd-108">Lync 2010 グループチャット (クライアント) を実行しているユーザーは、引き続き常設チャットサーバーのバックエンドサーバーに接続できます。</span><span class="sxs-lookup"><span data-stu-id="837fd-108">Users running Lync 2010 Group Chat (client) can then still connect to the Persistent Chat Server Back End Server.</span></span>

<span data-ttu-id="837fd-109">複数の常設チャットサーバーのエンドポイントを作成する必要はありません。常設チャットサーバープールごとに1つだけ必要です。</span><span class="sxs-lookup"><span data-stu-id="837fd-109">You don’t need to create multiple Persistent Chat Server endpoints; you just need one for each Persistent Chat Server pool.</span></span> <span data-ttu-id="837fd-110">管理者は複数のエンドポイント (プールごとに1つ) を作成できますが、従来のクライアントは一度に1つのプールにのみ接続するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="837fd-110">Administrators can create multiple endpoints (one per pool), but legacy clients can be configured to connect to only one pool at a time.</span></span> <span data-ttu-id="837fd-111">通常または主流のシナリオでは、従来の展開は1つのプールのみになります。</span><span class="sxs-lookup"><span data-stu-id="837fd-111">In the usual or mainstream scenario, the legacy deployment is one pool only.</span></span> <span data-ttu-id="837fd-112">新しい展開では、通常、そのプールを新しい Lync Server 2013 に移行し、別の新しい常設チャットサーバープールを追加することがあります。</span><span class="sxs-lookup"><span data-stu-id="837fd-112">A new deployment generally migrates that pool to a new Lync Server 2013 and might add some new additional Persistent Chat Server pools.</span></span>

<span data-ttu-id="837fd-113">一般的なシナリオでは、通常、次のパターンをたどります。</span><span class="sxs-lookup"><span data-stu-id="837fd-113">This mainstream scenario generally follows this pattern:</span></span>

  - <span data-ttu-id="837fd-114">1つの Lync Server 2010、グループチャットプール、および Lync 2010 グループチャットクライアントを使用してユーザーを管理するには、既知のユーザー (既定の sip: ocschat@\<domainName\>) を使用して、そのプールに接続します。</span><span class="sxs-lookup"><span data-stu-id="837fd-114">You administer users with one Lync Server 2010, Group Chat pool, and your Lync 2010 Group Chat clients connect to that pool by using some well-known user (either default sip:ocschat@\<domainName\>.com, or a similar one).</span></span> <span data-ttu-id="837fd-115">ユーザーは、SIP が有効な Active Directory ドメインサービスであり、参照サービスが着信要求を受信するために登録します。</span><span class="sxs-lookup"><span data-stu-id="837fd-115">The users are SIP-enabled Active Directory Domain Services, and the Lookup service registers with them to receive incoming requests.</span></span>

  - <span data-ttu-id="837fd-116">その後、Lync Server 2013 常設チャットサーバーと常設チャットサーバープールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="837fd-116">Subsequently, you install a Lync Server 2013 Persistent Chat Server and Persistent Chat Server pool.</span></span>

  - <span data-ttu-id="837fd-117">ユーザーが通常オフラインになる時間帯 (週末など) に次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="837fd-117">During a time when users are generally offline (for example, a weekend):</span></span>
    
      - <span data-ttu-id="837fd-118">Lync Server 2010、グループチャットをオフにします。</span><span class="sxs-lookup"><span data-stu-id="837fd-118">Turn off Lync Server 2010, Group Chat.</span></span>
    
      - <span data-ttu-id="837fd-119">Lync Server 2010 のグループチャットプールから Lync Server 2013 常設チャットサーバープールにデータを移行します。</span><span class="sxs-lookup"><span data-stu-id="837fd-119">Migrate data from the Lync Server 2010, Group Chat pool to the Lync Server 2013 Persistent Chat Server pool.</span></span>
    
      - <span data-ttu-id="837fd-120">Active Directory ドメインサービスから既知のユーザーを削除します。</span><span class="sxs-lookup"><span data-stu-id="837fd-120">Delete the well-known user from the Active Directory Domain Services.</span></span>
    
      - <span data-ttu-id="837fd-121">前の手順で削除した既知のユーザーと同じ SIP URI を持つ新しいレガシ エンドポイントを作成します。\*\*</span><span class="sxs-lookup"><span data-stu-id="837fd-121">Create a new *legacy endpoint* with the same SIP URI as the previously deleted well-known user.</span></span>
    
      - <span data-ttu-id="837fd-122">Lync Server 2013、常設チャットサーバーを起動します。</span><span class="sxs-lookup"><span data-stu-id="837fd-122">Start the Lync Server 2013, Persistent Chat Servers.</span></span>

  - <span data-ttu-id="837fd-123">ユーザーは、Lync 2010 グループチャット (クライアント) を使用してもう一度ログオンし、構成を変更することなくデータに接続します。</span><span class="sxs-lookup"><span data-stu-id="837fd-123">Users log back on by using their Lync 2010 Group Chat (client) and connect to their data without needing to change any configuration.</span></span>

  - <span data-ttu-id="837fd-124">後で、Lync Server 2010 のグループチャットを使用停止にすることができます。</span><span class="sxs-lookup"><span data-stu-id="837fd-124">At a later time, you can decommission the Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="837fd-125">その後、Lync Server 2013、常設チャットサーバーを展開し、新しい Lync Server 2013 常設チャットサーバープールをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="837fd-125">Subsequently, you can deploy Lync Server 2013, Persistent Chat Server, and install new Lync Server 2013 Persistent Chat Server pools.</span></span>

<span data-ttu-id="837fd-126">Lync Server 2010 からの移行の詳細については、「グループチャットから Lync Server 2013、常設チャットサーバーへの移行」を参照してください。「 [Lync server 2010、グループチャットまたは Office Communications server の 2007 R2 グループチャットから lync 2013 server への移行、常設チャットサーバーへの移行](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="837fd-126">For details about migrating from Lync Server 2010, Group Chat to Lync Server 2013, Persistent Chat Server, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="837fd-127">下位互換性を実行するには (従来のグループチャットプールクライアントが使用できる常設チャットサーバープールをポイントする常設チャットサーバーエンドポイントを作成するため):</span><span class="sxs-lookup"><span data-stu-id="837fd-127">To run backward compatibility (to create a Persistent Chat Server endpoint that points to a Persistent Chat Server pool, which can be used by legacy Group Chat pool clients):</span></span>

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

<span data-ttu-id="837fd-128">次に、その SIP アドレスを連絡先オブジェクトとして使用するように常設チャットクライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="837fd-128">Next, configure Persistent Chat clients to use that SIP address as their contact object.</span></span> <span data-ttu-id="837fd-129">SIP アドレスは、特定の常設チャットサーバープール用の**new-cspersistentchatendpoint**コマンドレットを使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="837fd-129">The SIP address is created with the **New-CsPersistentChatEndpoint** cmdlet for a specific Persistent Chat Server pool.</span></span>

<span data-ttu-id="837fd-130">Windows PowerShell コマンドラインインターフェイスを使用して常設チャットサーバーエンドポイントを追加するには、次の例を検討してください。</span><span class="sxs-lookup"><span data-stu-id="837fd-130">To add the Persistent Chat Server endpoint by using Windows PowerShell command-line interface, consider the following example.</span></span> <span data-ttu-id="837fd-131">この例では、プールの完全修飾ドメイン名 (FQDN) が "pcpool.contoso.com" である "contoso.com" トポロジで "persistentchat" という名前の連絡先オブジェクトを構成します。</span><span class="sxs-lookup"><span data-stu-id="837fd-131">In this case, you are configuring the contact object to be named "persistentchat" on the "contoso.com" topology, where the pool fully qualified domain name (FQDN) is "pcpool.contoso.com":</span></span>

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

<div>

## <a name="see-also"></a><span data-ttu-id="837fd-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="837fd-132">See Also</span></span>


[<span data-ttu-id="837fd-133">Lync Server 2010、グループ チャットまたは Office Communicatins Server 2007 R2 グループ チャットから Lync Server 2013、常設チャット サーバーへの移行</span><span class="sxs-lookup"><span data-stu-id="837fd-133">Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server</span></span>](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

