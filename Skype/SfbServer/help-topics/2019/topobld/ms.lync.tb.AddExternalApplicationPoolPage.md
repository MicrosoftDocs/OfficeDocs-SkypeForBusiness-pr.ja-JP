---
title: 信頼済みアプリケーション プールの FQDN を追加する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: 信頼済みアプリケーション プールの完全修飾ドメイン名 (FQDN) を定義するには、次のものを指定します。
ms.openlocfilehash: 575d4b5464b4a109bc34908f8cb86b802a20a5c0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122678"
---
# <a name="add-trusted-application-pool-fqdn"></a><span data-ttu-id="eafaf-103">信頼済みアプリケーション プールの FQDN の追加</span><span class="sxs-lookup"><span data-stu-id="eafaf-103">Add Trusted Application Pool FQDN</span></span>
 
<span data-ttu-id="eafaf-104">信頼済みアプリケーション プールの完全修飾ドメイン名 (FQDN) を定義するには、次のものを指定します。</span><span class="sxs-lookup"><span data-stu-id="eafaf-104">To define a Trusted Applications pool fully qualified domain name (FQDN), specify the following:</span></span>
  
<span data-ttu-id="eafaf-105">信頼済みアプリケーションをホストするサーバーまたはサーバー プールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="eafaf-105">An FQDN of the server or pool of servers that will host the trusted applications.</span></span>
  
<span data-ttu-id="eafaf-106">負荷分散や高可用性のために信頼済みアプリケーションのサーバー プールを展開する場合は、[**複数コンピューターのプール**] を選択します。負荷分散や高可用性が必要ない場合は、[**単一コンピューターのプール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eafaf-106">Select **Multiple computer pool** if you are deploying a pool of servers for the trusted applications from load balancing and high availability, or select **Single computer pool** if you do not need load balancing or high availability.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="eafaf-p101">信頼済みアプリケーションの単一サーバーを後でサーバー プールには変換できません。今後プールが必要になる可能性がある場合は、現状では単一のコンピューターのみ含まれる複数サーバー プールを展開し、必要に応じてサーバーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="eafaf-p101">A single Trusted Applications Server cannot be converted to a pool of servers later. If you think you may need a pool in the future, you can deploy a multiple server pool containing a single computer now, and add servers when needed.</span></span> 
  
<span data-ttu-id="eafaf-109">信頼済みアプリケーション プールの詳細については、「[New-CsTrustedApplicationPool](/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eafaf-109">For details about Trusted Applications pools, see [New-CsTrustedApplicationPool](/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span></span>
