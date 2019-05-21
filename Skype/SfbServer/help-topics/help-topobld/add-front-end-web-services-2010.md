---
title: フロントエンドの Web サービスの追加 (2010)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL がhttps://pool01.contoso.netの場合、ベース url は pool01.contoso.net になります。
ms.openlocfilehash: ec167b333948384a66f6ff66c64c4f53fcbe1076
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275326"
---
# <a name="add-front-end-web-services-2010"></a><span data-ttu-id="f54b4-104">フロントエンドの Web サービスの追加 (2010)</span><span class="sxs-lookup"><span data-stu-id="f54b4-104">Add Front End Web Services 2010</span></span>
 
<span data-ttu-id="f54b4-105">ベース URL は、https:// の部分を除いた URL の Web サービス ID です。</span><span class="sxs-lookup"><span data-stu-id="f54b4-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="f54b4-106">たとえば、プールの Web サービスの完全な URL がhttps://pool01.contoso.netの場合、ベース url は pool01.contoso.net になります。</span><span class="sxs-lookup"><span data-stu-id="f54b4-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="f54b4-107">Standard Edition サーバーの内部 Web サービスプールの完全修飾ドメイン名 (FQDN) を上書きすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f54b4-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition Server.</span></span> <span data-ttu-id="f54b4-108">Enterprise Edition のフロントエンドプールでドメインネームシステム (DNS) 負荷分散を構成している場合は、別の内部ベース URL (プールの FQDN と異なる場合があります。これはプールの FQDN と異なる\<ことがあり\>ます。これは、ベース url などの場合もあります)。</span><span class="sxs-lookup"><span data-stu-id="f54b4-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL (which must be different than the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="f54b4-109">ドメイン名を区別するために、内部ベース URL とは異なる外部ベース URL を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="f54b4-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="f54b4-110">たとえば、内部ドメインは contoso.net ですが、外部ドメイン名は contoso.com です。</span><span class="sxs-lookup"><span data-stu-id="f54b4-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="f54b4-111">外部ベース URL を定義するには、contoso.com ドメイン名を使用します。</span><span class="sxs-lookup"><span data-stu-id="f54b4-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="f54b4-112">これは、エッジ展開用のリバースプロキシサーバーにとって重要です。</span><span class="sxs-lookup"><span data-stu-id="f54b4-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="f54b4-113">外部ベース URL ドメイン名は、リバースプロキシの FQDN のドメイン名と同じにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f54b4-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="f54b4-114">インスタントメッセージングとプレゼンスを使用するには、フロントエンドプールへの HTTP アクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="f54b4-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

