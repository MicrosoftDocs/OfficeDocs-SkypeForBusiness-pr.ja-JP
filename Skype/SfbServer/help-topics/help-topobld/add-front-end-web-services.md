---
title: フロントエンドの Web サービスの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL がhttps://pool01.contoso.netの場合、ベース url は pool01.contoso.net になります。
ms.openlocfilehash: 3317df51fcacd17de8c1ce3f40163f2ce63dc13f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275284"
---
# <a name="add-front-end-web-services"></a><span data-ttu-id="f1b89-104">フロントエンドの Web サービスの追加</span><span class="sxs-lookup"><span data-stu-id="f1b89-104">Add Front End Web Services</span></span>
 
<span data-ttu-id="f1b89-105">ベース URL は、https:// の部分を除いた URL の Web サービス ID です。</span><span class="sxs-lookup"><span data-stu-id="f1b89-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="f1b89-106">たとえば、プールの Web サービスの完全な URL がhttps://pool01.contoso.netの場合、ベース url は pool01.contoso.net になります。</span><span class="sxs-lookup"><span data-stu-id="f1b89-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="f1b89-107">Standard Edition サーバーの内部 Web サービスプールの完全修飾ドメイン名 (FQDN) を上書きすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f1b89-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition server.</span></span> <span data-ttu-id="f1b89-108">Enterprise Edition のフロントエンドプールでドメインネームシステム (DNS) 負荷分散を構成する場合、別の内部ベース URL を指定することができます。この URL はプールの FQDN (内部\<のベース url\>など) とは異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="f1b89-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL, which must be different from the pool FQDN (for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="f1b89-109">ドメイン名を区別するために、内部ベース URL とは異なる外部ベース URL を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="f1b89-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="f1b89-110">たとえば、内部ドメインは contoso.net ですが、外部ドメイン名は contoso.com です。</span><span class="sxs-lookup"><span data-stu-id="f1b89-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="f1b89-111">Contoso.com ドメイン名を使用して、外部ベース URL を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="f1b89-111">You would define the external base URL using the contoso.com domain name.</span></span> <span data-ttu-id="f1b89-112">これは、エッジ展開用のリバースプロキシサーバーにとって重要です。</span><span class="sxs-lookup"><span data-stu-id="f1b89-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="f1b89-113">外部ベース URL ドメイン名は、リバースプロキシの FQDN のドメイン名と同じにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1b89-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="f1b89-114">インスタントメッセージングとプレゼンスを使用するには、フロントエンドプールへの HTTP アクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="f1b89-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

