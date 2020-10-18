---
title: DNS SRV レコードの更新
description: DNS SRV レコードを更新します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: 9542b91a-108c-4980-89ec-634905cbbf26
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688139(v=OCS.15)
ms:contentKeyID: 49733739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24161074e8f3bcf7e296a957588eeb59d5f2ad1b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579593"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="9cd52-103">DNS SRV レコードの更新</span><span class="sxs-lookup"><span data-stu-id="9cd52-103">Update DNS SRV records</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9cd52-104">_**トピックの最終更新日:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="9cd52-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="9cd52-105">この手順を正常に完了するには、Domain Admins グループまたは DnsAdmins グループのメンバーとしてサーバーまたはドメインにログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cd52-105">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="9cd52-106">このトピックでは、Lync Server 2013 に移行した後にドメインネームシステム (DNS) レコードを更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9cd52-106">This topic describes how to update the Domain Name System (DNS) records after migrating to Lync Server 2013.</span></span> <span data-ttu-id="9cd52-107">すべてのユーザーが Lync Server 2013 に移動された後、従来の Lync Server 2010 プールまたはディレクターが使用停止になる前に、すべての SIP ドメインについて内部 DNS の DNS SRV レコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cd52-107">After all users have been moved to Lync Server 2013, but before the legacy Lync Server 2010 pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="9cd52-108">この手順では、内部 DNS に SIP ユーザードメインのゾーンがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="9cd52-108">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<span data-ttu-id="9cd52-109">**DNS SRV レコードを構成するには**</span><span class="sxs-lookup"><span data-stu-id="9cd52-109">**To configure a DNS SRV record**</span></span>

1.  <span data-ttu-id="9cd52-110">DNS サーバー上で、[**スタート**] をクリックし、[**管理ツール**] をクリックします。次に、[**DNS**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cd52-110">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="9cd52-111">SIP ドメインのコンソールツリーで、[**前方参照ゾーン**] を展開し、Lync Server 2013 がインストールされている SIP ドメインを展開して、[ \*\* \_ tcp\*\* ] 設定に移動します。</span><span class="sxs-lookup"><span data-stu-id="9cd52-111">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Lync Server 2013 is installed, and navigate to the **\_tcp** setting.</span></span>

3.  <span data-ttu-id="9cd52-112">右側のウィンドウで、[ \*\* \_ sipinternaltls\*\* ] を右クリックし、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9cd52-112">In the right pane, right click **\_sipinternaltls** and select **Properties**.</span></span>

4.  <span data-ttu-id="9cd52-113">[ **このサービスを提供**しているホスト] で、Lync Server 2013 プールを指すようにホストの FQDN を更新します。</span><span class="sxs-lookup"><span data-stu-id="9cd52-113">In **Host offering this service**, update the host FQDN to point to the Lync Server 2013 pool.</span></span>

5.  <span data-ttu-id="9cd52-114">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cd52-114">Click **OK**.</span></span>

<span data-ttu-id="9cd52-115">**フロントエンド プールまたは Standard Edition サーバーの FQDN が解決できることを確認するには**</span><span class="sxs-lookup"><span data-stu-id="9cd52-115">**To verify that the FQDN of the Front End pool or Standard Edition server can be resolved**</span></span>

1.  <span data-ttu-id="9cd52-116">ドメイン内のクライアント コンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9cd52-116">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="9cd52-117">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cd52-117">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="9cd52-118">[**名前**] ボックスに「**cmd**」と入力し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cd52-118">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="9cd52-119">コマンドプロンプトで「 **nslookup** \<FQDN of the Front End pool\> または \<FQDN of the Standard Edition server\> 」と入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9cd52-119">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="9cd52-120">受け取る応答が、FQDN の適切な IP アドレスに解決しているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="9cd52-120">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

