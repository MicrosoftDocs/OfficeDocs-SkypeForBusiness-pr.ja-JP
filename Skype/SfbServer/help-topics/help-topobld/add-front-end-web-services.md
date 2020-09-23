---
title: フロントエンドの Web サービスを追加する
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
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL がの場合、 https://pool01.contoso.net ベース url は pool01.contoso.net になります。
ms.openlocfilehash: 45705ea940fa0f43f600546a680d76b41b645e59
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217938"
---
# <a name="add-front-end-web-services"></a><span data-ttu-id="c1851-104">フロントエンドの Web サービスを追加する</span><span class="sxs-lookup"><span data-stu-id="c1851-104">Add Front End Web Services</span></span>
 
<span data-ttu-id="c1851-105">ベース URL は、https:// の部分を除いた URL の Web サービス ID です。</span><span class="sxs-lookup"><span data-stu-id="c1851-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="c1851-106">たとえば、プールの Web サービスの完全な URL がの場合、 https://pool01.contoso.net ベース url は pool01.contoso.net になります。</span><span class="sxs-lookup"><span data-stu-id="c1851-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="c1851-107">Standard Edition サーバーの内部 Web サービスプールの完全修飾ドメイン名 (FQDN) を上書きすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c1851-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition server.</span></span> <span data-ttu-id="c1851-108">Enterprise Edition フロントエンドプールに対してドメインネームシステム (DNS) 負荷分散を構成している場合は、プールの FQDN (たとえば、内部) とは異なる内部ベースの URL を指定することができ \<your base URL\> ます。</span><span class="sxs-lookup"><span data-stu-id="c1851-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL, which must be different from the pool FQDN (for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="c1851-p104">内部ベース URL とは異なる外部ベース URL を指定して、ドメイン名前付けを区別できます。たとえば、内部ドメインが contoso.net でも、外部ドメイン名が contoso.com になっている場合は、contoso.com ドメイン名を使用して外部ベース URL を定義します。これは、エッジ展開でのリバース プロキシ サーバーで重要になります。外部ベース URL のドメイン名は、リバース プロキシの FQDN のドメイン名と同じである必要があります。インスタント メッセージングおよびプレゼンスでは、フロントエンド プールへの HTTP アクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="c1851-p104">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming. For example, your internal domain is contoso.net, but your external domain name is contoso.com. You would define the external base URL using the contoso.com domain name. This is important for reverse proxy servers for an edge deployment. The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy. Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

