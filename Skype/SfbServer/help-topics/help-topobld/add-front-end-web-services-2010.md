---
title: フロントエンドの Web サービスの追加 (2010)
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL は、 https://pool01.contoso.net、ベース URL は、pool01.contoso.net です。
ms.openlocfilehash: 75a905767ff4dbf2b9366193727bde370d05f87c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882798"
---
# <a name="add-front-end-web-services-2010"></a><span data-ttu-id="9b5ac-104">フロントエンドの Web サービスの追加 (2010)</span><span class="sxs-lookup"><span data-stu-id="9b5ac-104">Add Front End Web Services 2010</span></span>
 
<span data-ttu-id="9b5ac-105">ベース URL は、https:// の部分を除いた URL の Web サービス ID です。</span><span class="sxs-lookup"><span data-stu-id="9b5ac-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="9b5ac-106">たとえば、プールの Web サービスの完全な URL は、 https://pool01.contoso.net、ベース URL は、pool01.contoso.net です。</span><span class="sxs-lookup"><span data-stu-id="9b5ac-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="9b5ac-107">内部 Web サービス プール完全修飾ドメイン名 (FQDN) を Standard Edition Server を上書きすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9b5ac-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition Server.</span></span> <span data-ttu-id="9b5ac-108">ドメイン ネーム システム (DNS) の負荷分散、エンタープライズ エディションのフロント エンド プールを構成する場合は、内部の別の基本 URL を指定できます (プールの FQDN とは異なる必要があり、可能性があります、たとえば、内部の\<、ベース URL\>)。</span><span class="sxs-lookup"><span data-stu-id="9b5ac-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL (which must be different than the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="9b5ac-109">異なる外部ベース URL を指定する名前付け規則を区別するために、内部のベース URL から。</span><span class="sxs-lookup"><span data-stu-id="9b5ac-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="9b5ac-110">内部ドメインには、contoso.net、ですが、外部ドメイン名は、contoso.com などです。</span><span class="sxs-lookup"><span data-stu-id="9b5ac-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="9b5ac-111">Contoso.com ドメイン名を使用して外部ベース URL を定義します。</span><span class="sxs-lookup"><span data-stu-id="9b5ac-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="9b5ac-112">これは、エッジの展開のリバース プロキシ サーバーには重要です。</span><span class="sxs-lookup"><span data-stu-id="9b5ac-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="9b5ac-113">外部ベース URL のドメイン名は、リバース プロキシの FQDN のドメイン名と同じにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b5ac-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="9b5ac-114">インスタント メッセージングとプレゼンスのフロント エンド プールへの HTTP アクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="9b5ac-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

