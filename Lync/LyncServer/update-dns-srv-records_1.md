---
title: DNS SRV レコードを更新する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: a29149aa-30cc-4a59-af98-fb95c2385cce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688161(v=OCS.15)
ms:contentKeyID: 49733765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9df74033156e03cf7047b4d4bfbb2dbc83595b9b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a><span data-ttu-id="a0d5d-102">DNS SRV レコードを更新する</span><span class="sxs-lookup"><span data-stu-id="a0d5d-102">Update DNS SRV records</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0d5d-103">_**トピックの最終更新日:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="a0d5d-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="a0d5d-104">この手順を正常に完了するには、Domain Admins グループまたは DnsAdmins グループのメンバーとしてサーバーまたはドメインにログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0d5d-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="a0d5d-105">このトピックでは、Lync Server 2013 に移行した後にドメインネームシステム (DNS) レコードを更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0d5d-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Lync Server 2013.</span></span> <span data-ttu-id="a0d5d-106">すべてのユーザーが Lync Server 2013 に移動された後、従来の Office Communications Server 2007 R2 プールまたはディレクターが使用停止になる前に、すべての SIP ドメインについて内部 DNS の DNS SRV レコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0d5d-106">After all users have been moved to Lync Server 2013, but before the legacy Office Communications Server 2007 R2 pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="a0d5d-107">この手順では、内部 DNS に SIP ユーザードメインのゾーンがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="a0d5d-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<span data-ttu-id="a0d5d-108">**DNS SRV レコードを構成するには**</span><span class="sxs-lookup"><span data-stu-id="a0d5d-108">**To configure a DNS SRV record**</span></span>

1.  <span data-ttu-id="a0d5d-109">DNS サーバー上で、[**スタート**] をクリックし、[**管理ツール**] をクリックします。次に、[**DNS**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0d5d-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="a0d5d-110">SIP ドメインのコンソールツリーで、[**前方参照ゾーン**] を展開し、Lync Server 2013 がインストールされている SIP ドメインを展開して、[ \*\* \_tcp\*\* ] 設定に移動します。</span><span class="sxs-lookup"><span data-stu-id="a0d5d-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Lync Server 2013 is installed, and navigate to the **\_tcp** setting.</span></span>

3.  <span data-ttu-id="a0d5d-111">右側のウィンドウで、[ \*\* \_sipinternaltls\*\* ] を右クリックし、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0d5d-111">In the right pane, right click **\_sipinternaltls** and select **Properties**.</span></span>

4.  <span data-ttu-id="a0d5d-112">[**このサービスを提供**しているホスト] で、Lync Server 2013 プールを指すようにホストの FQDN を更新します。</span><span class="sxs-lookup"><span data-stu-id="a0d5d-112">In **Host offering this service**, update the host FQDN to point to the Lync Server 2013 pool.</span></span>

5.  <span data-ttu-id="a0d5d-113">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0d5d-113">Click **OK**.</span></span>

<span data-ttu-id="a0d5d-114">**フロントエンド プールまたは Standard Edition サーバーの FQDN が解決できることを確認するには**</span><span class="sxs-lookup"><span data-stu-id="a0d5d-114">**To verify that the FQDN of the Front End pool or Standard Edition server can be resolved**</span></span>

1.  <span data-ttu-id="a0d5d-115">ドメイン内のクライアント コンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a0d5d-115">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="a0d5d-116">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0d5d-116">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="a0d5d-117">[**名前**] ボックスに「**cmd**」と入力し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0d5d-117">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="a0d5d-118">コマンドプロンプトで、Standard Edition サーバー \<\>のフロントエンドプール\>または fqdn の「 **nslookup** \<fqdn」と入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a0d5d-118">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="a0d5d-119">受け取る応答が、FQDN の適切な IP アドレスに解決しているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="a0d5d-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

