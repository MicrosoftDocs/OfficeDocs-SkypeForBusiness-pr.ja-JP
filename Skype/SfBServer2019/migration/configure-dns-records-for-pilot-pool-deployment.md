---
title: パイロット プール展開の DNS レコードの構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: パイロット プールを展開するには、前にパイロットのプールの DNS ホスト A のエントリを更新する必要があります。 この手順を正常に完了するには、サーバーまたはドメイン管理者グループのメンバーまたは DnsAdmins グループのメンバーとしてドメインにログオンする必要があります。
ms.openlocfilehash: 23ac5e4f85dc0da560b4d288bbfad426298bf82e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30872740"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="a2817-104">パイロット プール展開の DNS レコードの構成</span><span class="sxs-lookup"><span data-stu-id="a2817-104">Configure DNS records for pilot pool deployment</span></span>

<span data-ttu-id="a2817-105">パイロット プールを展開するには、前にパイロットのプールの DNS ホスト A のエントリを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2817-105">Before deploying the pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="a2817-106">この手順を正常に完了するには、サーバーまたはドメイン管理者グループのメンバーまたは DnsAdmins グループのメンバーとしてドメインにログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2817-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
### <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="a2817-107">DNS ホスト A レコードを構成するのには</span><span class="sxs-lookup"><span data-stu-id="a2817-107">To configure DNS Host A records</span></span>

1. <span data-ttu-id="a2817-108">ドメイン ネーム システム (DNS) サーバー上 [**スタート**] ボタンを選択し、 **[管理ツール**] をクリックし、[ **DNS**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2817-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="a2817-109">ドメインのコンソール ツリーで **[前方参照ゾーン**] を展開し、ビジネス サーバー 2019 の Skype をインストールするドメインを右クリックし、します。</span><span class="sxs-lookup"><span data-stu-id="a2817-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Skype for Business Server 2019 will be installed.</span></span>
    
3. <span data-ttu-id="a2817-110">[**新しいホスト (A または AAAA)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2817-110">Click **New Host (A or AAAA)**.</span></span>
    
4. <span data-ttu-id="a2817-111">**名**をクリックして、(ドメイン名は、ゾーンをレコードで定義されている A レコードの一部として入力する必要はありませんからと仮定します) ビジネス サーバー 2019 プールの Skype のホスト名を入力します。</span><span class="sxs-lookup"><span data-stu-id="a2817-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>
    
5. <span data-ttu-id="a2817-112">**IP アドレス**] をクリックし、フロント エンド プールの IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="a2817-112">Click **IP Address**, and then type the IP address for the Front End pool.</span></span>
    
6. <span data-ttu-id="a2817-113">**ホストの追加**をクリックし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2817-113">Click **Add Host**, and then click **OK**.</span></span> 
    
7. <span data-ttu-id="a2817-114">終了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2817-114">When you are finished, click **Done**.</span></span>
    

