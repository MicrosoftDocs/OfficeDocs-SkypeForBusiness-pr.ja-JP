---
title: フロント エンド Web サービスを追加します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL は、 https://pool01.contoso.net、ベース URL は、pool01.contoso.net です。
ms.openlocfilehash: 6626bb14221aaa909219451d26b76b0cd15bc576
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-web-services"></a><span data-ttu-id="0f542-104">フロント エンド Web サービスを追加します。</span><span class="sxs-lookup"><span data-stu-id="0f542-104">Add Front End Web Services</span></span>
 
<span data-ttu-id="0f542-105">ベース URL は、https:// の部分を除いた URL の Web サービス ID です。</span><span class="sxs-lookup"><span data-stu-id="0f542-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="0f542-106">たとえば、プールの Web サービスの完全な URL は、 https://pool01.contoso.net、ベース URL は、pool01.contoso.net です。</span><span class="sxs-lookup"><span data-stu-id="0f542-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="0f542-107">内部 Web サービス プール完全修飾ドメイン名 (FQDN) Standard Edition サーバーではオーバーライドできません。</span><span class="sxs-lookup"><span data-stu-id="0f542-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition server.</span></span> <span data-ttu-id="0f542-108">ドメイン ネーム システム (DNS) の負荷分散、エンタープライズ エディションのフロント エンド プールを構成する場合は、異なる内部ベース URL が、プールの FQDN とは異なる必要がありますを指定できます (たとえば、内部の\<、ベース URL\>)。</span><span class="sxs-lookup"><span data-stu-id="0f542-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL, which must be different from the pool FQDN (for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="0f542-109">異なる外部ベース URL を指定する名前付け規則を区別するために、内部のベース URL から。</span><span class="sxs-lookup"><span data-stu-id="0f542-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="0f542-110">内部ドメインには、contoso.net、ですが、外部ドメイン名は、contoso.com などです。Contoso.com ドメイン名を使用して外部ベース URL を定義します。</span><span class="sxs-lookup"><span data-stu-id="0f542-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com. You would define the external base URL using the contoso.com domain name.</span></span> <span data-ttu-id="0f542-111">これは、エッジの展開のリバース プロキシ サーバーには重要です。</span><span class="sxs-lookup"><span data-stu-id="0f542-111">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="0f542-112">外部ベース URL のドメイン名は、リバース プロキシの FQDN のドメイン名と同じにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f542-112">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="0f542-113">インスタント メッセージングとプレゼンスのフロント エンド プールへの HTTP アクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="0f542-113">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

