---
title: ディレクター Web サービスの追加
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL は、 https://pool01.contoso.net、ベース URL は、pool01.contoso.net です。
ms.openlocfilehash: d87f4948fd2e619ce6aba99b556a9ed0af0fd098
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30926533"
---
# <a name="add-director-web-service"></a><span data-ttu-id="0f116-104">ディレクター Web サービスの追加</span><span class="sxs-lookup"><span data-stu-id="0f116-104">Add Director Web Service</span></span>
 
<span data-ttu-id="0f116-105">ベース URL は、https:// の部分を除いた URL の Web サービス ID です。</span><span class="sxs-lookup"><span data-stu-id="0f116-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="0f116-106">たとえば、プールの Web サービスの完全な URL は、 https://pool01.contoso.net、ベース URL は、pool01.contoso.net です。</span><span class="sxs-lookup"><span data-stu-id="0f116-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="0f116-107">単一のディレクターを展開する場合は、内部の Web サービス プール完全修飾ドメイン名 (FQDN) をオーバーライドできません。</span><span class="sxs-lookup"><span data-stu-id="0f116-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="0f116-108">内部の別のベース URL を指定するには、ドメイン ネーム システム (DNS) の負荷分散ディレクターのプールを構成する場合 (とプールの FQDN とは異なる必要があります可能性があります、たとえば、内部の\<、ベース URL\>)。</span><span class="sxs-lookup"><span data-stu-id="0f116-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="0f116-109">異なる外部ベース URL を指定する名前付け規則を区別するために、内部のベース URL から。</span><span class="sxs-lookup"><span data-stu-id="0f116-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="0f116-110">内部ドメインには、contoso.net、ですが、外部ドメイン名は、contoso.com などです。</span><span class="sxs-lookup"><span data-stu-id="0f116-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="0f116-111">Contoso.com ドメイン名を使用して外部ベース URL を定義します。</span><span class="sxs-lookup"><span data-stu-id="0f116-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="0f116-112">これは、エッジの展開のリバース プロキシ サーバーには重要です。</span><span class="sxs-lookup"><span data-stu-id="0f116-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="0f116-113">外部ベース URL のドメイン名は、リバース プロキシの FQDN のドメイン名と同じにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f116-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  

