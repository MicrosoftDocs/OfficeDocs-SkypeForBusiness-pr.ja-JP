---
title: フロント エンド Web サービス 2010 を追加します。
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL は、 https://pool01.contoso.net、ベース URL は、pool01.contoso.net です。
ms.openlocfilehash: 5d5c935d1357c2baf66ed17ab762db8fd442ac67
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2018
ms.locfileid: "19976894"
---
# <a name="add-front-end-web-services-2010"></a><span data-ttu-id="60e9b-104">フロント エンド Web サービス 2010 を追加します。</span><span class="sxs-lookup"><span data-stu-id="60e9b-104">Add Front End Web Services 2010</span></span>
 
<span data-ttu-id="60e9b-105">ベース URL は、https:// の部分を除いた URL の Web サービス ID です。</span><span class="sxs-lookup"><span data-stu-id="60e9b-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="60e9b-106">たとえば、プールの Web サービスの完全な URL は、 https://pool01.contoso.net、ベース URL は、pool01.contoso.net です。</span><span class="sxs-lookup"><span data-stu-id="60e9b-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="60e9b-107">内部 Web サービス プール完全修飾ドメイン名 (FQDN) を Standard Edition Server を上書きすることはできません。</span><span class="sxs-lookup"><span data-stu-id="60e9b-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition Server.</span></span> <span data-ttu-id="60e9b-108">ドメイン ネーム システム (DNS) の負荷分散、エンタープライズ エディションのフロント エンド プールを構成する場合は、内部の別の基本 URL を指定できます (プールの FQDN とは異なる必要があり、可能性があります、たとえば、内部の\<、ベース URL\>)。</span><span class="sxs-lookup"><span data-stu-id="60e9b-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL (which must be different than the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="60e9b-109">異なる外部ベース URL を指定する名前付け規則を区別するために、内部のベース URL から。</span><span class="sxs-lookup"><span data-stu-id="60e9b-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="60e9b-110">内部ドメインには、contoso.net、ですが、外部ドメイン名は、contoso.com などです。</span><span class="sxs-lookup"><span data-stu-id="60e9b-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="60e9b-111">Contoso.com ドメイン名を使用して外部ベース URL を定義します。</span><span class="sxs-lookup"><span data-stu-id="60e9b-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="60e9b-112">これは、エッジの展開のリバース プロキシ サーバーには重要です。</span><span class="sxs-lookup"><span data-stu-id="60e9b-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="60e9b-113">外部ベース URL のドメイン名は、リバース プロキシの FQDN のドメイン名と同じにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="60e9b-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="60e9b-114">インスタント メッセージングとプレゼンスのフロント エンド プールへの HTTP アクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="60e9b-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

