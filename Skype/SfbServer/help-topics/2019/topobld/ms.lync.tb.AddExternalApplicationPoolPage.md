---
title: 信頼済みアプリケーション プールの FQDN の追加
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: 信頼されたアプリケーション プールの完全修飾ドメイン名 (FQDN) を定義するには、次のように指定します。
ms.openlocfilehash: 12ea56f285dfffbe78b74c8eece8211a8676333e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895832"
---
# <a name="add-trusted-application-pool-fqdn"></a><span data-ttu-id="278d8-103">信頼済みアプリケーション プールの FQDN の追加</span><span class="sxs-lookup"><span data-stu-id="278d8-103">Add Trusted Application Pool FQDN</span></span>
 
<span data-ttu-id="278d8-104">信頼されたアプリケーション プールの完全修飾ドメイン名 (FQDN) を定義するには、次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="278d8-104">To define a Trusted Applications pool fully qualified domain name (FQDN), specify the following:</span></span>
  
<span data-ttu-id="278d8-105">サーバーまたは信頼されたアプリケーションをホストするサーバー プールの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="278d8-105">An FQDN of the server or pool of servers that will host the trusted applications.</span></span>
  
<span data-ttu-id="278d8-106">負荷分散と高可用性は、信頼されたアプリケーション サーバーのプールを展開する、または負荷分散や高可用性が必要ない場合は、 **1 台のコンピューターのプール**を選択する場合は、**複数コンピューターのプール**を選択します。</span><span class="sxs-lookup"><span data-stu-id="278d8-106">Select **Multiple computer pool** if you are deploying a pool of servers for the trusted applications from load balancing and high availability, or select **Single computer pool** if you do not need load balancing or high availability.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="278d8-107">1 つの信頼されたアプリケーション サーバーは、後で、サーバーのプールに変換できません。</span><span class="sxs-lookup"><span data-stu-id="278d8-107">A single Trusted Applications Server cannot be converted to a pool of servers later.</span></span> <span data-ttu-id="278d8-108">プールは、将来的にする必要がある場合は、ここで、1 台のコンピューターを含む複数のサーバー プールを展開し、必要なときにサーバーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="278d8-108">If you think you may need a pool in the future, you can deploy a multiple server pool containing a single computer now, and add servers when needed.</span></span> 
  
<span data-ttu-id="278d8-109">信頼されたアプリケーション プールに関する詳細情報は、[新規 CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="278d8-109">For details about Trusted Applications pools, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span></span>
  

