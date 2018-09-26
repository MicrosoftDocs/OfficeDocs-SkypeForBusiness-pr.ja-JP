---
title: DNS SRV レコードを更新します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: この手順を正常に完了するには、サーバーまたはドメイン管理者グループのメンバーまたは DnsAdmins グループのメンバーとしてドメインにログオンする必要があります。
ms.openlocfilehash: f298db10f7030482b604734a1719756af4071ce2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027229"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="bdcc7-103">DNS SRV レコードを更新します。</span><span class="sxs-lookup"><span data-stu-id="bdcc7-103">Update DNS SRV records</span></span>

<span data-ttu-id="bdcc7-104">この手順を正常に完了するには、サーバーまたはドメイン管理者グループのメンバーまたは DnsAdmins グループのメンバーとしてドメインにログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bdcc7-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
<span data-ttu-id="bdcc7-105">このトピックでは、ビジネス サーバー 2019 の Skype に移行した後、ドメイン ネーム システム (DNS) レコードを更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bdcc7-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="bdcc7-106">すべてのユーザーが Skype をビジネス サーバー 2019 に移動した後ですが、従来のプールまたはディレクターの使用を中止する前に、内部 SIP ドメインごとに DNS に DNS SRV レコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bdcc7-106">After all users have been moved to Skype for Business Server 2019, but before the legacy pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="bdcc7-107">この手順では、内部 DNS が、SIP ユーザー ドメインのゾーンを持っていると仮定します。</span><span class="sxs-lookup"><span data-stu-id="bdcc7-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>
  
## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="bdcc7-108">DNS SRV レコードを構成するのには</span><span class="sxs-lookup"><span data-stu-id="bdcc7-108">To configure a DNS SRV record</span></span>

1. <span data-ttu-id="bdcc7-109">DNS サーバーで [**スタート**] ボタンを選択し、 **[管理ツール**] をクリックし、[ **DNS**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bdcc7-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="bdcc7-110">SIP ドメインのコンソール ツリーで **[前方参照ゾーン**を展開し、ビジネス サーバー 2019 をインストールし、 **「_tcp」** 設定に移動する Skype の SIP ドメインを展開します。</span><span class="sxs-lookup"><span data-stu-id="bdcc7-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Skype for Business Server 2019 is installed, and navigate to the **_tcp** setting.</span></span> 
    
3. <span data-ttu-id="bdcc7-111">右側のウィンドウでは、 **_sipinternaltls**を右クリックし、**プロパティ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="bdcc7-111">In the right pane, right-click **_sipinternaltls** and select **Properties**.</span></span>
    
4. <span data-ttu-id="bdcc7-112">**このサービスを提供しているホスト**を、ホストの FQDN がプールのビジネス サーバー 2019 Skype を指すように更新します。</span><span class="sxs-lookup"><span data-stu-id="bdcc7-112">In **Host offering this service**, update the host FQDN to point to the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="bdcc7-113">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bdcc7-113">Click **OK**.</span></span>
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="bdcc7-114">フロント エンド プールまたは Standard Edition サーバーの FQDN を解決できることを確認するには</span><span class="sxs-lookup"><span data-stu-id="bdcc7-114">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1. <span data-ttu-id="bdcc7-115">ドメイン内のクライアント コンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="bdcc7-115">Log on to a client computer in the domain.</span></span>
    
2. <span data-ttu-id="bdcc7-116">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bdcc7-116">Click **Start**, and then click **Run**.</span></span>
    
3. <span data-ttu-id="bdcc7-117">**[名前**] ボックスに cmd と入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bdcc7-117">In the **Open** box, type cmd, and then click **OK**.</span></span>
    
4. <span data-ttu-id="bdcc7-118">コマンド プロンプトで nslookup と入力します。_\<フロント エンド プールの FQDN\>_ または_\<Standard Edition サーバーの FQDN\>_、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="bdcc7-118">At the command prompt, type nslookup _\<FQDN of the Front End pool\>_ or  _\<FQDN of the Standard Edition server\>_, and then press ENTER.</span></span>
    
5. <span data-ttu-id="bdcc7-119">FQDN の適切な IP アドレスに解決することを示すメッセージが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bdcc7-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>
    

