---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: Skype for Business Server 2015 のほとんどのサーバーの役割に関する高可用性の主なスキームは、プールによるサーバーの冗長性に基づいています。 あるサーバーの役割を実行しているサーバーに障害が発生すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。
ms.openlocfilehash: 4b10eab9e2de3741958e2ed17cfc92aa430ed3ea
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816396"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="a79bf-104">High Availability (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="a79bf-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="a79bf-105">Skype for Business Server 2015 のほとんどのサーバーの役割に関する高可用性の主なスキームは、プールによるサーバーの冗長性に基づいています。</span><span class="sxs-lookup"><span data-stu-id="a79bf-105">The main high availability scheme for most server roles in Skype for Business Server 2015 is based on server redundancy via pooling.</span></span> <span data-ttu-id="a79bf-106">あるサーバーの役割を実行しているサーバーに障害が発生すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。</span><span class="sxs-lookup"><span data-stu-id="a79bf-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="a79bf-107">高可用性を有効にするには、Skype for Business Server 2015 で少なくとも2台のフロントエンドサーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="a79bf-107">Skype for Business Server 2015 requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="a79bf-108">計画ツールでは、高可用性をサポートするために追加のサーバーが追加されるかどうかを判断するために、次の条件を使用します。</span><span class="sxs-lookup"><span data-stu-id="a79bf-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="a79bf-109">展開に2台以上のフロントエンドサーバーが含まれている場合、計画ツールでは追加のサーバーは追加されません。</span><span class="sxs-lookup"><span data-stu-id="a79bf-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="a79bf-110">展開にエッジサーバーが含まれている場合は、追加のサーバーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="a79bf-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="a79bf-111">展開に永続的なチャットが含まれている場合、計画ツールでは、余分なサーバーが追加されますが、プール番号は増えません。</span><span class="sxs-lookup"><span data-stu-id="a79bf-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="a79bf-112">たとえば、展開に既に4台のサーバーが含まれている場合、計画ツールでは、(合計5台の) サーバーを追加することが推奨されますが、1つのプールを維持します。</span><span class="sxs-lookup"><span data-stu-id="a79bf-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 
    
<span data-ttu-id="a79bf-113">計画ツールでは、すべてのデータベースのミラー SQL データベースも追加されます。</span><span class="sxs-lookup"><span data-stu-id="a79bf-113">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="a79bf-114">たとえば、フロントエンドの SQL Server データベースがある場合は、計画ツールによって、そのデータベースがこのデータベースのミラーデータベースとして追加され、"フロントエンドミラー SQL データベース" という名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="a79bf-114">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="a79bf-115">高可用性を実現するための環境の準備について詳しくは、「 [Skype For Business Server 2015 で高可用性と障害回復を計画する](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a79bf-115">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

