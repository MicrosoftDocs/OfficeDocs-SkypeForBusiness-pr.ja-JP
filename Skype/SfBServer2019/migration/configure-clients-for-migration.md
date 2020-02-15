---
title: 移行用にクライアントを構成する
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
description: このトピックでは、Skype for Business Server 2019 に移行する前に実行する必要がある、推奨されるクライアントの展開手順について説明します。 これらの構成の変更は、Lync Server 2013 または Skype for Business Server 2015 で行う必要があります。
ms.openlocfilehash: ad3ed4f34409b5ba730d79c24db65092802572db
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "41986092"
---
# <a name="configure-clients-for-migration"></a><span data-ttu-id="12497-104">移行用にクライアントを構成する</span><span class="sxs-lookup"><span data-stu-id="12497-104">Configure clients for migration</span></span>

<span data-ttu-id="12497-105">このトピックでは、Skype for Business Server 2019 に移行する前に実行する必要がある、推奨されるクライアントの展開手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="12497-105">This topic contains the recommended client deployment steps you should take before migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="12497-106">これらの構成の変更は、Lync Server 2013 または Skype for Business Server 2015 (移行**元**のバージョン) で行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="12497-106">These configuration changes should be made on Lync Server 2013 or Skype for Business Server 2015 (the version you are migrating **from**).</span></span>
  
### <a name="to-configure-clients-before-migration"></a><span data-ttu-id="12497-107">移行の前にクライアントを構成するには</span><span class="sxs-lookup"><span data-stu-id="12497-107">To configure clients before migration</span></span>

1. <span data-ttu-id="12497-108">既存のインストールについて、最新のサーバー、クライアント、およびデバイスの更新プログラム (ホットフィックス) を展開します。</span><span class="sxs-lookup"><span data-stu-id="12497-108">Deploy the most recent server, client, and device updates (hotfixes) for your existing installation.</span></span>
    
2. <span data-ttu-id="12497-109">以前のバージョンの Skype for Business Server では、クライアントバージョンフィルターを使用して、最新の更新プログラムがインストールされているクライアントのみを許可します。</span><span class="sxs-lookup"><span data-stu-id="12497-109">On the previous version of Skype for Business Server, use Client Version Filtering to only allow clients with the most current updates installed.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="12497-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="12497-110">See also</span></span>

<span data-ttu-id="12497-111">[Lync 2013 の新しい設定と変更された設定](https://technet.microsoft.com/library/jj205204(v=ocs.15).aspx)</span><span class="sxs-lookup"><span data-stu-id="12497-111">[New and changed settings for Lync 2013](https://technet.microsoft.com/library/jj205204(v=ocs.15).aspx)</span></span> 
 
<span data-ttu-id="12497-112">[Lync 2013 でのクライアントの相互運用性](https://technet.microsoft.com/library/jj204672(v=ocs.15).aspx)
 </span><span class="sxs-lookup"><span data-stu-id="12497-112">[Client interoperability in Lync 2013](https://technet.microsoft.com/library/jj204672(v=ocs.15).aspx)
 </span></span><!-- The above links point to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->

 [<span data-ttu-id="12497-113">クライアントとデバイスの計画</span><span class="sxs-lookup"><span data-stu-id="12497-113">Plan for clients and devices</span></span>](../../SfbServer/plan-your-deployment/clients-and-devices/clients-and-devices.md)
