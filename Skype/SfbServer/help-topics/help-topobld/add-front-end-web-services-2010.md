---
title: フロント エンドの Web サービスの追加 (2010)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL が次の場合、ベース https://pool01.contoso.net URL はpool01.contoso.net。
ms.openlocfilehash: 96a258cd2d3c46d700dff32ea4adb6213b4de9b1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824027"
---
# <a name="add-front-end-web-services-2010"></a><span data-ttu-id="63a73-104">フロント エンドの Web サービスの追加 (2010)</span><span class="sxs-lookup"><span data-stu-id="63a73-104">Add Front End Web Services 2010</span></span>
 
<span data-ttu-id="63a73-105">ベース URL は、https:// の部分を除いた URL の Web サービス ID です。</span><span class="sxs-lookup"><span data-stu-id="63a73-105">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="63a73-106">たとえば、プールの Web サービスの完全な URL が次の場合、ベース https://pool01.contoso.net URL はpool01.contoso.net。</span><span class="sxs-lookup"><span data-stu-id="63a73-106">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>
  
<span data-ttu-id="63a73-107">Standard Edition サーバーの内部 Web サービス プールの完全修飾ドメイン名 (FQDN) を上書きすることはできません。</span><span class="sxs-lookup"><span data-stu-id="63a73-107">You cannot override the internal Web Services pool fully qualified domain name (FQDN) for a Standard Edition Server.</span></span> <span data-ttu-id="63a73-108">Enterprise Edition フロントエンド プールに対してドメイン ネーム システム (DNS) 負荷分散を構成する場合は、別の内部ベース URL (プールの FQDN とは異なる必要があります。内部 URL など) を指定できます。 \<your base URL\></span><span class="sxs-lookup"><span data-stu-id="63a73-108">If you are configuring Domain Name System (DNS) load balancing for an Enterprise Edition Front End pool, you can specify a different internal base URL (which must be different than the pool FQDN and could be, for example, internal-\<your base URL\>).</span></span>
  
<span data-ttu-id="63a73-109">内部ベース URL とは異なる外部ベース URL を指定して、ドメイン名前付けを区別できます。</span><span class="sxs-lookup"><span data-stu-id="63a73-109">You can specify an external base URL that is different it from your internal base URL to differentiate domain naming.</span></span> <span data-ttu-id="63a73-110">たとえば、内部ドメインは contoso.net ですが、外部ドメイン名は contoso.com という場合があります。</span><span class="sxs-lookup"><span data-stu-id="63a73-110">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="63a73-111">ドメイン名 contoso.com を使用して、外部ベース URL を定義しています。</span><span class="sxs-lookup"><span data-stu-id="63a73-111">You would define the external base URL by using the contoso.com domain name.</span></span> <span data-ttu-id="63a73-112">これは、エッジ展開でのリバース プロキシ サーバーで重要になります。</span><span class="sxs-lookup"><span data-stu-id="63a73-112">This is important for reverse proxy servers for an edge deployment.</span></span> <span data-ttu-id="63a73-113">外部ベース URL のドメイン名は、リバース プロキシの FQDN のドメイン名と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="63a73-113">The external base URL domain name should be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="63a73-114">インスタント メッセージングとプレゼンスでは、フロント エンド プールへの HTTP アクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="63a73-114">Instant messaging and presence requires HTTP access to the Front End pool.</span></span>
  

