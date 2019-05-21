---
title: ディレクター Web サービスの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL がhttps://pool01.contoso.netの場合、ベース url は pool01.contoso.net になります。
ms.openlocfilehash: 6d4b99446e4c64f6185c58bd82ef9ca59cadb28c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304745"
---
# <a name="add-director-web-service"></a><span data-ttu-id="bab67-104">ディレクター Web サービスの追加</span><span class="sxs-lookup"><span data-stu-id="bab67-104">Add Director Web Service</span></span>
 
<span data-ttu-id="bab67-105">ベース URL は、https:// の部分を除いた URL の Web サービス ID です。</span><span class="sxs-lookup"><span data-stu-id="bab67-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="bab67-106">たとえば、プールの Web サービスの完全な URL がhttps://pool01.contoso.netの場合、ベース url は pool01.contoso.net になります。</span><span class="sxs-lookup"><span data-stu-id="bab67-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="bab67-107">1つのディレクターのみを展開する場合は、内部 Web サービスプールの完全修飾ドメイン名 (FQDN) を上書きすることはできません。</span><span class="sxs-lookup"><span data-stu-id="bab67-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="bab67-108">ディレクターのプールのドメインネームシステム (DNS) 負荷分散を構成する場合は、別の内部ベース URL を指定できます (プールの FQDN とは異なる場合があります。これは、プールの\<FQDN とは\>異なる場合があります。これは、内部のベース url などの場合もあります)。</span><span class="sxs-lookup"><span data-stu-id="bab67-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="bab67-109">ドメイン名を区別するために、内部ベース URL とは異なる外部ベース URL を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="bab67-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="bab67-110">たとえば、内部ドメインは contoso.net ですが、外部ドメイン名は contoso.com です。</span><span class="sxs-lookup"><span data-stu-id="bab67-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="bab67-111">外部ベース URL を定義するには、contoso.com ドメイン名を使用します。</span><span class="sxs-lookup"><span data-stu-id="bab67-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="bab67-112">これは、エッジ展開用のリバースプロキシサーバーにとって重要です。</span><span class="sxs-lookup"><span data-stu-id="bab67-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="bab67-113">外部ベース URL ドメイン名は、リバースプロキシの FQDN のドメイン名と同じにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bab67-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  

