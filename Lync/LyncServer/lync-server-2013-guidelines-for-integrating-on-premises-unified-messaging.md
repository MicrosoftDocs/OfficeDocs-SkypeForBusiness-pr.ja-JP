---
title: 'Lync Server 2013: オンプレミスのユニファイドメッセージングを統合するためのガイドライン'
description: 'Lync Server 2013: オンプレミスのユニファイドメッセージングを統合するためのガイドライン。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Guidelines for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398656(v=OCS.15)
ms:contentKeyID: 48184681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 814c927aa36199737712328d3b92c64a8e967a55
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576643"
---
# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="66b57-103">オンプレミスのユニファイドメッセージングと Lync Server 2013 を統合するためのガイドライン</span><span class="sxs-lookup"><span data-stu-id="66b57-103">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66b57-104">_**トピックの最終更新日:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="66b57-104">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="66b57-105">エンタープライズ Voip を展開する際に考慮すべきガイドラインとベストプラクティスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="66b57-105">The following are guidelines and best practices to consider when you deploy Enterprise Voice:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="66b57-106">Exchange ユニファイドメッセージング (UM) は、UCMA 4 も使用している場合にのみ、IPv6 をサポートします。</span><span class="sxs-lookup"><span data-stu-id="66b57-106">Exchange Unified Messaging (UM) supports IPv6 only if you are also using UCMA 4.</span></span>



</div>

  - <span data-ttu-id="66b57-107">Lync Server 2013 Standard Edition サーバーまたはフロントエンドプールを展開します。</span><span class="sxs-lookup"><span data-stu-id="66b57-107">Deploy a Lync Server 2013 Standard Edition server or a Front End pool.</span></span> <span data-ttu-id="66b57-108">インストールの詳細については、「展開」のドキュメントの「 [展開 Lync Server 2013](lync-server-2013-deploying-lync-server.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66b57-108">For details about installation, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="66b57-109">スムーズに問題なく統合できるように、Exchange 管理者と協力して、各自が実施する作業を確認します。</span><span class="sxs-lookup"><span data-stu-id="66b57-109">Work with Exchange administrators to confirm which tasks each of you will perform to assure a smooth and successful integration.</span></span>

  - <span data-ttu-id="66b57-110">Exchange UM に対してユーザーを有効にする各 Exchange ユニファイドメッセージング (UM) フォレストに、Exchange メールボックスサーバーの役割を展開します。</span><span class="sxs-lookup"><span data-stu-id="66b57-110">Deploy the Exchange Mailbox server roles in each Exchange Unified Messaging (UM) forest where you want to enable users for Exchange UM.</span></span> <span data-ttu-id="66b57-111">Exchange server の役割のインストールの詳細については、Microsoft Exchange Server 2013 のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="66b57-111">For details about installing Exchange server roles, see the Microsoft Exchange Server 2013 documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="66b57-112">Exchange ユニファイドメッセージング (UM) がインストールされている場合、自己署名証明書を使用するように構成されます。</span><span class="sxs-lookup"><span data-stu-id="66b57-112">When Exchange Unified Messaging (UM) is installed, it is configured to use a self-signed certificate.</span></span><BR><span data-ttu-id="66b57-113">ただし、自己署名証明書では、Lync Server 2013 と Exchange UM が相互に信頼することはできません。このため、両方のサーバーが信頼する証明機関に対して個別の証明書を要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66b57-113">The self-signed certificate, however, does not enable Lync Server 2013 and Exchange UM to trust each other, which is why it is necessary to request a separate certificate from a certification authority that both servers trust.</span></span>

    
    </div>

  - <span data-ttu-id="66b57-114">Lync Server 2013 と Exchange UM が異なるフォレストにインストールされている場合は、各 exchange フォレストが Lync Server 2013 フォレストと Lync Server 2013 フォレストを信頼するように構成して、各 Exchange フォレストを信頼するようにします。</span><span class="sxs-lookup"><span data-stu-id="66b57-114">If Lync Server 2013 and Exchange UM are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest and the Lync Server 2013 forest to trust each Exchange forest.</span></span> <span data-ttu-id="66b57-115">また、通常は、スクリプトまたは Id ライフサイクルマネージャー (ILM) などのフォレスト間ツールを使用して、Lync Server 2013 フォレスト内のユーザーオブジェクトに対するユーザーの Exchange UM 設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="66b57-115">Also, set the users’ Exchange UM settings on the user objects in the Lync Server 2013 forest, typically by using a script or a cross-forest tool, such as Identity Lifecycle Manager (ILM).</span></span>

  - <span data-ttu-id="66b57-116">必要に応じて、ユニファイド メッセージング サーバーを管理するのに Exchange 管理コンソールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="66b57-116">If necessary, install the Exchange Management Console to manage your Unified Messaging servers.</span></span>

  - <span data-ttu-id="66b57-117">Outlook Voice Access および自動応答の有効な電話番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="66b57-117">Obtain valid phone numbers for Outlook Voice Access and auto attendant.</span></span>

  - <span data-ttu-id="66b57-118">Microsoft Exchange Server 2010 Service Pack 1 (SP1) より前のバージョンの Exchange UM を使用している場合は、Exchange UM SIP URI ダイヤルプランおよびエンタープライズ Voip ダイヤルプランの名前を調整します。</span><span class="sxs-lookup"><span data-stu-id="66b57-118">If you are using a version of Exchange UM earlier than Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordinate names for Exchange UM SIP URI dial plans and Enterprise Voice dial plans.</span></span>

<div>

## <a name="deploying-redundant-exchange-um-servers"></a><span data-ttu-id="66b57-119">冗長 Exchange UM サーバーの展開</span><span class="sxs-lookup"><span data-stu-id="66b57-119">Deploying Redundant Exchange UM Servers</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="66b57-120">組織に対して構成する Exchange UM SIP URI ダイヤルプランごとに、Exchange UM サービスが実行されているサーバーを少なくとも2台展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="66b57-120">We recommend that you deploy a minimum of two servers on which Exchange UM services is running for each Exchange UM SIP URI dial plan that you configure for your organization.</span></span> <span data-ttu-id="66b57-121">拡張された容量の提供に加えて、冗長サーバーを展開すると高可用性が得られます。</span><span class="sxs-lookup"><span data-stu-id="66b57-121">In addition to providing expanded capacity, deploying redundant servers provides high availability.</span></span> <span data-ttu-id="66b57-122">サーバー障害が発生した場合、Lync Server 2013 を別のサーバーにフェールオーバーするように構成できます。</span><span class="sxs-lookup"><span data-stu-id="66b57-122">In the event of an server failure, Lync Server 2013 can be configured to fail over to another server.</span></span>



</div>

<span data-ttu-id="66b57-123">次に示すのは、Exchange UM の復元性を提供する構成例です。</span><span class="sxs-lookup"><span data-stu-id="66b57-123">The following example configurations provide Exchange UM resiliency.</span></span>

<span data-ttu-id="66b57-124">**例 1: Exchange UM の復元性**</span><span class="sxs-lookup"><span data-stu-id="66b57-124">**Example 1: Exchange UM Resiliency**</span></span>

<span data-ttu-id="66b57-125">![Exchange UM の例1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange UM の例1")</span><span class="sxs-lookup"><span data-stu-id="66b57-125">![Exchange UM Example 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange UM Example 1")</span></span>

<span data-ttu-id="66b57-126">例1では、データセンターで Exchange UM サーバー1と2が有効になっており、Dublin データセンターで Exchange UM サーバー3と4が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="66b57-126">In Example 1, Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center.</span></span> <span data-ttu-id="66b57-127">Tuで Exchange UM が停止した場合、サーバー1と2のドメインネームシステム (DNS) A レコードは、それぞれサーバー3と4をポイントするように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66b57-127">In the event of an Exchange UM outage in Tukwila, the Domain Name System (DNS) A records for servers 1 and 2 should be configured to point to servers 3 and 4, respectively.</span></span> <span data-ttu-id="66b57-128">Dublin で Exchange UM が停止した場合、サーバー3と4の DNS A レコードは、それぞれサーバー1と2をポイントするように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66b57-128">In the event of an Exchange UM outage in Dublin, the DNS A records for servers 3 and 4 should be configured to point to servers 1 and 2, respectively.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="66b57-129">例 1 の場合はまた、それぞれの Exchange UM サーバーで次の証明書のうちの 1 つを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="66b57-129">For Example 1, you should also assign one of following certificate on each Exchange UM server:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="66b57-130">サブジェクト名の別名 (SAN) に、ワイルドカードの証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="66b57-130">Use a certificate with a wildcard in the Subject Alternative Name (SAN).</span></span></P>
> <LI>
> <P><span data-ttu-id="66b57-131">SAN 内の4台の Exchange UM サーバーそれぞれの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="66b57-131">Put the fully qualified domain name (FQDN) of each of the four Exchange UM servers in the SAN.</span></span></P></LI></UL>



</div>

<span data-ttu-id="66b57-132">**例 2:Exchange UM の復元性**</span><span class="sxs-lookup"><span data-stu-id="66b57-132">**Example 2: Exchange UM Resiliency**</span></span>

<span data-ttu-id="66b57-133">![Exchange UM の例2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange UM の例2")</span><span class="sxs-lookup"><span data-stu-id="66b57-133">![Exchange UM Example 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange UM Example 2")</span></span>

<span data-ttu-id="66b57-p106">例 2 では、通常の操作条件の下、Exchange UM サーバー 1 と 2 は Tukwila のデータ センターで有効化されています。Exchange UM サーバー 3 と 4 は Dublin のデータ センターで有効化されています。 4 台すべてのサーバーが Tukwila のユーザーの SIP URL ダイヤル プランに含まれていますが、サーバー3 と 4 は有効化されていません。 たとえば、Tukwila で Exchange UM サーバーが停止した場合、Exchange UM サーバー 1 と 2 は無効化され、Tukwila の Exchange UM トラフィックが Dublin のサーバーにルーティングされるよう、Exchange UM サーバー 3 と 4 は有効化されます。</span><span class="sxs-lookup"><span data-stu-id="66b57-p106">In Example 2, under ordinary operating conditions Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. All four servers are included in the Tukwila users' SIP URI dial plan; however, servers 3 and 4 are disabled. In the event of an Exchange UM outage in Tukwila, for example, Exchange UM servers 1 and 2 should be disabled and Exchange UM servers 3 and 4 should be enabled so the Tukwila Exchange UM traffic will be routed to the servers in Dublin.</span></span>

<span data-ttu-id="66b57-137">Exchange 2013 でユニファイドメッセージングを有効または無効にする方法の詳細については、「」の「Exchange 2013 UM と Lync Server の統合」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372) 。</span><span class="sxs-lookup"><span data-stu-id="66b57-137">For details about how to enable or disable Unified Messaging on Exchange 2013, see “Integrate Exchange 2013 UM with Lync Server” at [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

<span data-ttu-id="66b57-138">Microsoft Exchange Server 2010 でユニファイドメッセージングを有効または無効にする方法の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66b57-138">For details about how to enable or disable Unified Messaging on Microsoft Exchange Server 2010, see:</span></span>

  - <span data-ttu-id="66b57-139">「Exchange 2010 でユニファイドメッセージングを有効 [https://go.microsoft.com/fwlink/p/?LinkId=204418](https://go.microsoft.com/fwlink/p/?linkid=204418) にする」</span><span class="sxs-lookup"><span data-stu-id="66b57-139">"Enable Unified Messaging on Exchange 2010" at [https://go.microsoft.com/fwlink/p/?LinkId=204418](https://go.microsoft.com/fwlink/p/?linkid=204418).</span></span>

  - <span data-ttu-id="66b57-140">「Exchange 2010 でユニファイドメッセージングを無効 [https://go.microsoft.com/fwlink/p/?LinkId=204416](https://go.microsoft.com/fwlink/p/?linkid=204416) にする」</span><span class="sxs-lookup"><span data-stu-id="66b57-140">"Disable Unified Messaging on Exchange 2010" at [https://go.microsoft.com/fwlink/p/?LinkId=204416](https://go.microsoft.com/fwlink/p/?linkid=204416).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="66b57-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="66b57-141">See Also</span></span>


[<span data-ttu-id="66b57-142">オンプレミスのユニファイドメッセージングと Lync Server 2013 を統合するための展開プロセス</span><span class="sxs-lookup"><span data-stu-id="66b57-142">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

