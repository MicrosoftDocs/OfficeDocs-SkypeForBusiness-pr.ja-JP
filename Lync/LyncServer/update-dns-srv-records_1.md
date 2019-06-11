---
title: DNS SRV レコードの更新
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Update DNS SRV records
ms:assetid: a29149aa-30cc-4a59-af98-fb95c2385cce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688161(v=OCS.15)
ms:contentKeyID: 49733765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97ff3eed81a90960444b260bd0ca5b9c4c67022e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a><span data-ttu-id="5fb32-102">DNS SRV レコードの更新</span><span class="sxs-lookup"><span data-stu-id="5fb32-102">Update DNS SRV records</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fb32-103">_**最終更新日:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="5fb32-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="5fb32-104">この手順を完了するには、サーバーまたはドメインに、Domain Admins グループのメンバーまたは DnsAdmins グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fb32-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="5fb32-105">このトピックでは、Lync Server 2013 に移行した後に、ドメインネームシステム (DNS) レコードを更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5fb32-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Lync Server 2013.</span></span> <span data-ttu-id="5fb32-106">すべてのユーザーが Lync Server 2013 に移動された後、従来の Office Communications Server 2007 R2 プールまたはディレクターが廃止される前に、すべての SIP ドメインの内部 DNS の DNS SRV レコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fb32-106">After all users have been moved to Lync Server 2013, but before the legacy Office Communications Server 2007 R2 pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="5fb32-107">この手順では、内部 DNS に SIP ユーザードメイン用のゾーンが含まれていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="5fb32-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<span data-ttu-id="5fb32-108">**DNS SRV レコードを構成するには**</span><span class="sxs-lookup"><span data-stu-id="5fb32-108">**To configure a DNS SRV record**</span></span>

1.  <span data-ttu-id="5fb32-109">DNS サーバーで [**スタート**] をクリックし、[**管理ツール**]、[ **dns**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fb32-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="5fb32-110">Sip ドメインのコンソールツリーで [**前方参照ゾーン**] を展開し、Lync Server 2013 がインストールされている SIP ドメインを展開して、[ \*\* \_tcp\*\* ] 設定に移動します。</span><span class="sxs-lookup"><span data-stu-id="5fb32-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Lync Server 2013 is installed, and navigate to the **\_tcp** setting.</span></span>

3.  <span data-ttu-id="5fb32-111">右側のウィンドウで、[ \*\* \_sipinternaltls\*\* ] を右クリックし、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fb32-111">In the right pane, right click **\_sipinternaltls** and select **Properties**.</span></span>

4.  <span data-ttu-id="5fb32-112">[**このサービスを提供**しているホスト] で、Lync Server 2013 プールを指すようにホストの FQDN を更新します。</span><span class="sxs-lookup"><span data-stu-id="5fb32-112">In **Host offering this service**, update the host FQDN to point to the Lync Server 2013 pool.</span></span>

5.  <span data-ttu-id="5fb32-113">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fb32-113">Click **OK**.</span></span>

<span data-ttu-id="5fb32-114">**フロントエンドプールまたは Standard Edition サーバーの FQDN が解決できることを確認するには**</span><span class="sxs-lookup"><span data-stu-id="5fb32-114">**To verify that the FQDN of the Front End pool or Standard Edition server can be resolved**</span></span>

1.  <span data-ttu-id="5fb32-115">ドメイン内のクライアントコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5fb32-115">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="5fb32-116">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fb32-116">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="5fb32-117">[**開く**] ボックスに**cmd**と入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fb32-117">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="5fb32-118">コマンドプロンプトに、標準エディションサーバー \<\>のフロントエンドプール\>または fqdn の**nslookup** \<FQDN と入力して、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5fb32-118">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="5fb32-119">FQDN の適切な IP アドレスに解決される返信を受信したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fb32-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

