---
title: 高可用性 (計画ツール)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: Skype for Business Server 2015 のほとんどのサーバーの役割の主な高可用性スキームは、プールによるサーバーの冗長性に基づいて行います。 あるサーバーの役割を実行しているサーバーが失敗すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。
ms.openlocfilehash: b50ccf145f1197531fe91218d2e99c8b0739c15c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834747"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="056aa-104">高可用性 (計画ツール)</span><span class="sxs-lookup"><span data-stu-id="056aa-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="056aa-105">Skype for Business Server 2015 のほとんどのサーバーの役割の主な高可用性スキームは、プールによるサーバーの冗長性に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="056aa-105">The main high availability scheme for most server roles in Skype for Business Server 2015 is based on server redundancy via pooling.</span></span> <span data-ttu-id="056aa-106">あるサーバーの役割を実行しているサーバーが失敗すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。</span><span class="sxs-lookup"><span data-stu-id="056aa-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="056aa-107">Skype for Business Server 2015 では、高可用性を実現するために少なくとも 2 台のフロントエンド サーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="056aa-107">Skype for Business Server 2015 requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="056aa-108">計画ツールは、次の条件を使用して、高可用性をサポートするためにサーバーを追加するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="056aa-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="056aa-109">展開に 2 つ以上のフロントエンド サーバーが含まれる場合、計画ツールは追加のサーバーを追加しません。</span><span class="sxs-lookup"><span data-stu-id="056aa-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="056aa-110">展開にエッジ サーバーが含まれている場合は、追加のサーバーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="056aa-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="056aa-111">展開に常設チャットが含まれている場合、計画ツールは追加のサーバーを追加しますが、プール番号は増やしません。</span><span class="sxs-lookup"><span data-stu-id="056aa-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="056aa-112">たとえば、展開に既に 4 台のサーバーが含まれている場合、計画ツールは (合計 5 台のサーバーに対して) サーバーを追加し、1 つのプールを維持します。</span><span class="sxs-lookup"><span data-stu-id="056aa-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 
    
<span data-ttu-id="056aa-113">また、計画ツールは、すべてのデータベースSQLミラー データベースを追加します。</span><span class="sxs-lookup"><span data-stu-id="056aa-113">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="056aa-114">たとえば、フロントエンド SQL Server データベースがある場合、計画ツールは、他のデータベースをこのデータベースのミラー データベースとして追加し、"Front End mirror SQL database" という名前を付きます。</span><span class="sxs-lookup"><span data-stu-id="056aa-114">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="056aa-115">高可用性を実現するための環境の準備の詳細については [、「Plan for high availability and disaster recovery in Skype for Business Server 2015」](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="056aa-115">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

