---
title: フロントエンドの Web サービスの追加 (2010)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL がの場合、 https://pool01.contoso.net ベース url は pool01.contoso.net になります。
ms.openlocfilehash: d87bb3716a19f59f2614194d79dfedaf544964e1
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217958"
---
# <a name="add-front-end-web-services-2010"></a><span data-ttu-id="5c027-104">フロントエンドの Web サービスの追加 (2010)</span><span class="sxs-lookup"><span data-stu-id="5c027-104">Add Front End Web Services 2010</span></span>
 
<span data-ttu-id="5c027-105">ベース URL は、https:// の部分を除いた URL の Web サービス ID です。</span><span class="sxs-lookup"><span data-stu-id="5c027-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="5c027-106">たとえば、プールの Web サービスの完全な URL がの場合、 https://pool01.contoso.net ベース url は pool01.contoso.net になります。</span><span class="sxs-lookup"><span data-stu-id="5c027-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="5c027-107">Standard Edition サーバーの内部 Web サービスプールの完全修飾ドメイン名 (FQDN) を上書きすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5c027-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition Server.</span></span> <span data-ttu-id="5c027-108">Enterprise Edition フロントエンドプールに対してドメインネームシステム (DNS) 負荷分散を構成している場合は、異なる内部ベース URL を指定できます (プールの FQDN とは異なる必要があり、たとえば、内部 \<your base URL\> )。</span><span class="sxs-lookup"><span data-stu-id="5c027-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL (which must be different than the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="5c027-109">内部ベース URL とは異なる外部ベース URL を指定して、ドメイン名前付けを区別できます。</span><span class="sxs-lookup"><span data-stu-id="5c027-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="5c027-110">たとえば、内部ドメインは contoso.net ですが、外部ドメイン名は contoso.com という場合があります。</span><span class="sxs-lookup"><span data-stu-id="5c027-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="5c027-111">ドメイン名 contoso.com を使用して、外部ベース URL を定義しています。</span><span class="sxs-lookup"><span data-stu-id="5c027-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="5c027-112">これは、エッジ展開でのリバース プロキシ サーバーで重要になります。</span><span class="sxs-lookup"><span data-stu-id="5c027-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="5c027-113">外部ベース URL のドメイン名は、リバース プロキシの FQDN のドメイン名と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c027-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="5c027-114">インスタントメッセージングとプレゼンスは、フロントエンドプールへの HTTP アクセスを必要とします。</span><span class="sxs-lookup"><span data-stu-id="5c027-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

