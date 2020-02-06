---
title: パイロット プール展開の DNS レコードの構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: パイロットプールを展開する前に、パイロットプールの DNS Host エントリを更新する必要があります。 この手順を完了するには、サーバーまたはドメインに、Domain Admins グループのメンバーまたは DnsAdmins グループのメンバーとしてログオンしている必要があります。
ms.openlocfilehash: 94e5047dc82b0ddb55b03ad5c466011878c05ae7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813855"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="c7a1f-104">パイロット プール展開の DNS レコードの構成</span><span class="sxs-lookup"><span data-stu-id="c7a1f-104">Configure DNS records for pilot pool deployment</span></span>

<span data-ttu-id="c7a1f-105">パイロットプールを展開する前に、パイロットプールの DNS Host A エントリを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7a1f-105">Before deploying the pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="c7a1f-106">この手順を完了するには、サーバーまたはドメインに、Domain Admins グループのメンバーまたは DnsAdmins グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7a1f-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
### <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="c7a1f-107">DNS ホスト A レコードを構成するには</span><span class="sxs-lookup"><span data-stu-id="c7a1f-107">To configure DNS Host A records</span></span>

1. <span data-ttu-id="c7a1f-108">ドメインネームシステム (DNS) サーバーで、[**スタート**] をクリックし、[**管理ツール**]、[ **DNS**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7a1f-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="c7a1f-109">ドメインのコンソールツリーで [**前方参照ゾーン**] を展開し、Skype For business Server 2019 がインストールされているドメインを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="c7a1f-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Skype for Business Server 2019 will be installed.</span></span>
    
3. <span data-ttu-id="c7a1f-110">[**新しいホスト (A または AAAA)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7a1f-110">Click **New Host (A or AAAA)**.</span></span>
    
4. <span data-ttu-id="c7a1f-111">[**名前**] をクリックし、Skype For business Server 2019 プールのホスト名を入力します (ドメイン名は、レコードが定義されていて、A レコードの一部として入力する必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="c7a1f-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>
    
5. <span data-ttu-id="c7a1f-112">[ **Ip アドレス**] をクリックして、フロントエンドプールの ip アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="c7a1f-112">Click **IP Address**, and then type the IP address for the Front End pool.</span></span>
    
6. <span data-ttu-id="c7a1f-113">[**ホストの追加**] をクリックし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7a1f-113">Click **Add Host**, and then click **OK**.</span></span> 
    
7. <span data-ttu-id="c7a1f-114">完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7a1f-114">When you are finished, click **Done**.</span></span>
    

