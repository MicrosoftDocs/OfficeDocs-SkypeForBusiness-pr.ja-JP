---
title: Hosted Exchange UM との統合のための DNS SRV レコードを作成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a DNS SRV record for integration with hosted Exchange UM
ms:assetid: 8ea590ae-58ea-4ca5-9853-e0708b3ea760
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh500728(v=OCS.15)
ms:contentKeyID: 48184770
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac215b5a0ba42ff031962e656e72fb355a808bf4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507474"
---
# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a><span data-ttu-id="21f36-102">Hosted Exchange UM との統合のための DNS SRV レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="21f36-102">Create a DNS SRV record for integration with hosted Exchange UM</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21f36-103">_**トピックの最終更新日:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="21f36-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="21f36-104">このトピックでは、Lync Server 2013 エッジサーバーが Microsoft Exchange Online などのホストされた Exchange サービスにルーティングするために必要なドメインネームシステム (DNS) SRV レコードを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="21f36-104">This topic describes how to configure the Domain Name System (DNS) SRV record that is required for a Lync Server 2013 Edge Server to route to a hosted Exchange service such as Microsoft Exchange Online.</span></span>

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a><span data-ttu-id="21f36-105">Hosted Exchange サービス用の外部 DNS SRV レコードを作成するには</span><span class="sxs-lookup"><span data-stu-id="21f36-105">To create an external DNS SRV record for the hosted Exchange service</span></span>

1.  <span data-ttu-id="21f36-106">DnsAdmins グループのメンバーとして外部 DNS サーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="21f36-106">Log on to the external DNS server as a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="21f36-107">[**スタート**]、[**管理ツール**]、[**DNS**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="21f36-107">Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="21f36-108">SIP ドメインのコンソールツリーで、[ **前方参照ゾーン**] を展開し、Lync Server 2013 をインストールする SIP ドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="21f36-108">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and select the SIP domain in which Lync Server 2013 will be installed.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="21f36-p101">Lync Server がインストールされているか Lync Server がインストールされる SIP ドメインに DNS SRV レコードを作成する必要があります。SRV レコードを作成するときに、[このサービスを提供しているホスト] フィールドで使用する FQDN には、エッジ プールの外部 FQDN を指定する必要があります。たとえば、エッジ プールの外部 FQDN が edge01.contoso.net の場合、その値を入力します。また、これは、DNS ホスト (A) レコードと同じドメインに含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="21f36-p101">You must create the DNS SRV record in the SIP domain in which Lync Server is or will be installed. When you create the SRV record, the FQDN used for the Host offering this service field must be the external FQDN of the Edge pool. For example, if the external FQDN of your Edge pool is edge01.contoso.net, enter that value. This must also be in the same domain as the DNS Hosts (A) record.</span></span>

    
    </div>

4.  <span data-ttu-id="21f36-113">選択したドメインを右クリックし、[**その他の新しいレコード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21f36-113">Right-click the selected domain, and then click **Other New Records**.</span></span>

5.  <span data-ttu-id="21f36-114">[**リソース レコードの種類**] で、[**サービス ロケーション (SRV)**]、[**レコードの作成**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="21f36-114">In **Resource Record Type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

6.  <span data-ttu-id="21f36-115">[**新しいリソースレコード**] で、[**サービス**] をクリックし、「 \*\* \_ sipfederationtls\*\*」と入力します。</span><span class="sxs-lookup"><span data-stu-id="21f36-115">In **New Resource Record**, click **Service**, and then type **\_sipfederationtls**.</span></span>

7.  <span data-ttu-id="21f36-116">[**プロトコル**] をクリックし、「 \*\* \_ tcp\*\*」と入力します。</span><span class="sxs-lookup"><span data-stu-id="21f36-116">Click **Protocol**, and then type **\_tcp**.</span></span>

8.  <span data-ttu-id="21f36-117">"**ポート番号**" フィールドをクリックし、「**5061**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="21f36-117">Click **Port Number**, and then type **5061**.</span></span>

9.  <span data-ttu-id="21f36-118">[ **このサービスを提供**しているホスト] をクリックし、lync Server 2013 エッジプールの完全修飾ドメイン名 (FQDN) を入力します。これにより、信頼できる外部クライアントに対して lync server 2013 システムへのアクセスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="21f36-118">Click **Host offering this service**, and then type the fully qualified domain name (FQDN) of the Lync Server 2013 Edge pool that provides access to your Lync Server 2013 system for trusted external clients.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="21f36-119">このドメインを、Exchange Online 設定内で権限のある承認済みドメインとしてセットアップする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="21f36-119">The domain must also be set up as an authoritative, accepted domain in your Exchange Online settings.</span></span> <span data-ttu-id="21f36-120">詳細については、「の承認済みドメインを作成する」を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=229762">https://go.microsoft.com/fwlink/p/?linkId=229762</A> 。</span><span class="sxs-lookup"><span data-stu-id="21f36-120">For details, see Create Accepted Domains at <A href="https://go.microsoft.com/fwlink/p/?linkid=229762">https://go.microsoft.com/fwlink/p/?linkId=229762</A>.</span></span>

    
    </div>

10. <span data-ttu-id="21f36-121">**[OK]** をクリックしてから、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21f36-121">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a><span data-ttu-id="21f36-122">DNS SRV レコードが正常に作成されたことを確認するには</span><span class="sxs-lookup"><span data-stu-id="21f36-122">To verify that the DNS SRV record was created successfully</span></span>

1.  <span data-ttu-id="21f36-123">ドメイン内のクライアント コンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="21f36-123">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="21f36-124">**[スタート]** ボタンをクリックし、**[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21f36-124">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="21f36-125">コマンド プロンプトで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="21f36-125">At the command prompt, run the following command:</span></span>
    
        nslookup <FQDN Lync Edge Pool>

4.  <span data-ttu-id="21f36-126">受け取る応答が、FQDN の適切な IP アドレスに解決しているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="21f36-126">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="21f36-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="21f36-127">See Also</span></span>


[<span data-ttu-id="21f36-128">Lync Server 2013 でリバースプロキシサーバーの DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="21f36-128">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

