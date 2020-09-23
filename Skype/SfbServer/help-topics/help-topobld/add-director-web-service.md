---
title: ディレクター Web サービスの追加
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
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL がの場合、 https://pool01.contoso.net ベース url は pool01.contoso.net になります。
ms.openlocfilehash: 5d965eb591afca8d7154d8fd12af741ddaf65084
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219468"
---
# <a name="add-director-web-service"></a><span data-ttu-id="a345f-104">ディレクター Web サービスの追加</span><span class="sxs-lookup"><span data-stu-id="a345f-104">Add Director Web Service</span></span>
 
<span data-ttu-id="a345f-105">ベース URL は、https:// の部分を除いた URL の Web サービス ID です。</span><span class="sxs-lookup"><span data-stu-id="a345f-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="a345f-106">たとえば、プールの Web サービスの完全な URL がの場合、 https://pool01.contoso.net ベース url は pool01.contoso.net になります。</span><span class="sxs-lookup"><span data-stu-id="a345f-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="a345f-107">1つのディレクターのみを展開する場合は、内部 Web サービスプールの完全修飾ドメイン名 (FQDN) を無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a345f-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) if you are deploying only a single Director.</span></span> <span data-ttu-id="a345f-108">ディレクタープールのドメインネームシステム (DNS) 負荷分散を構成している場合は、別の内部ベース URL を指定できます (プールの FQDN とは異なる必要があり、たとえば内部-など \<your base URL\> )。</span><span class="sxs-lookup"><span data-stu-id="a345f-108">If you are configuring a Domain Name System (DNS) load balancing for pool of Directors, you can specify a different internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="a345f-p104">内部ベース URL とは異なる外部ベース URL を指定して、ドメイン名前付けを区別できます。たとえば、内部ドメインは contoso.net ですが、外部ドメイン名は contoso.com という場合があります。ドメイン名 contoso.com を使用して、外部ベース URL を定義しています。これは、エッジ展開でのリバース プロキシ サーバーで重要になります。外部ベース URL のドメイン名は、リバース プロキシの FQDN のドメイン名と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a345f-p104">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming. For example, your internal domain is contoso.net, but your external domain name is contoso.com. You would define the external base URL by using the contoso.com domain name. This is important for reverse proxy servers for an edge deployment. The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> 
  

